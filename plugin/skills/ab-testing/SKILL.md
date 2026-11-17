---
name: ab-testing
description: "Lên kế hoạch, chạy hoặc đọc thử nghiệm A/B, hoặc khi cần phán đoán: kết quả có thật không, dừng được chưa, phiên bản nào thắng, có đáng thử không: cỡ mẫu, thời gian, ý nghĩa thống kê, giả thuyết, danh sách thử nghiệm, thử khi traffic ít, tránh ngày sale lớn. Thiết lập đo lường xem analytics; sửa chuyển đổi trên trang xem cro."
metadata:
  version: 1.0.0
  upstream: ab-testing 2.0.7
---

# Thử nghiệm A/B

Bạn là chuyên gia thử nghiệm. Mục tiêu: thiết kế thử nghiệm cho kết quả hợp lệ về thống kê và hành động được.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán); chỉ hỏi phần còn thiếu:
1. **Bối cảnh** — muốn cải thiện gì, định thay đổi gì
2. **Hiện trạng** — tỷ lệ chuyển đổi nền, lượng traffic
3. **Ràng buộc** — độ phức tạp kỹ thuật, thời hạn, công cụ

**Thực tế với nhiều SME Việt:** traffic website thường không đủ cho A/B test chuẩn. Tính cỡ mẫu trước; nếu không đủ, xem phần "Khi traffic không đủ" thay vì chạy thử nghiệm sẽ không bao giờ kết luận được.

---

## Nguyên tắc cốt lõi

1. **Bắt đầu bằng giả thuyết** — dự đoán cụ thể, dựa trên lập luận hoặc dữ liệu; không phải "thử xem sao".
2. **Thử một thứ** — một biến mỗi thử nghiệm, nếu không sẽ không biết cái gì có tác dụng.
3. **Nghiêm ngặt thống kê** — xác định cỡ mẫu trước; không nhìn trộm rồi dừng sớm; giữ đúng phương pháp đã chọn.
4. **Đo thứ quan trọng** — chỉ số chính gắn giá trị kinh doanh; chỉ số phụ để hiểu; chỉ số bảo vệ để không gây hại.

## Khung giả thuyết

```
Vì [quan sát/dữ liệu],
chúng tôi tin rằng [thay đổi]
sẽ dẫn tới [kết quả mong đợi]
với [đối tượng].
Ta biết là đúng khi [chỉ số].
```

**Yếu:** "Đổi màu nút có thể tăng lượt bấm."
**Mạnh:** "Vì khách nói khó tìm nút đặt hàng (bản đồ nhiệt và phản hồi qua chat), chúng tôi tin làm nút to hơn, màu tương phản sẽ tăng ≥15% lượt bấm với khách mới trên điện thoại. Đo bằng tỷ lệ từ xem trang tới bắt đầu đặt hàng."

## Loại thử nghiệm

| Loại | Mô tả | Traffic cần |
|---|---|---|
| A/B | Hai phiên bản, một thay đổi | Vừa |
| A/B/n | Nhiều biến thể | Cao hơn |
| MVT (đa biến) | Nhiều thay đổi tổ hợp | Rất cao |
| Split URL | Biến thể ở URL khác nhau | Vừa |

## Cỡ mẫu

| Tỷ lệ nền | Tăng 10% | Tăng 20% | Tăng 50% |
|---|---|---|---|
| 1% | 160k/biến thể | 43k/biến thể | 7,7k/biến thể |
| 3% | 53k | 14k | 2,5k |
| 5% | 31k | 8,2k | 1,5k |
| 10% | 15k | 3,8k | 690 |

Mỗi biến thể, độ tin cậy 95% (hai phía), lực kiểm định 80%. Mức tăng là tương đối (3% → 3,6% là tăng 20%). Công cụ tính: [Evan Miller](https://www.evanmiller.org/ab-testing/sample-size.html), [Optimizely](https://www.optimizely.com/sample-size-calculator/) — hoặc tính bằng code. Bảng chi tiết và cách tính thời gian: [references/sample-size-guide.md](references/sample-size-guide.md) (tiếng Anh).

**Thời gian:** chạy đủ ít nhất 1–2 chu kỳ tuần trọn vẹn. **Tránh để thử nghiệm vắt qua ngày sale lớn** (ngày đôi 9/9, 10/10, 11/11, 12/12, Black Friday, Tết, lương về) — hành vi khách khác hẳn, kết quả không khái quát được; hoặc bắt đầu/kết thúc ngoài các mốc đó, hoặc phân tích riêng.

### Khi traffic không đủ
- **Thử thay đổi lớn hơn** (thông điệp, ưu đãi, cấu trúc trang) — hiệu ứng lớn cần mẫu nhỏ hơn nhiều.
- **Thử ở nơi có lượng lớn:** nội dung quảng cáo (tính năng thử nghiệm A/B của Meta, TikTok, Google), tiêu đề email, mẫu tin Zalo/SMS, ảnh và tiêu đề sản phẩm trên sàn.
- **Đo chỉ số gần hơn** (bấm nút, thêm giỏ) thay vì đơn hàng — nhưng nói rõ đó là chỉ số đại diện.
- **Thử nghiệm định tính:** 5 người dùng thật làm nhiệm vụ trên trang (xem `customer-research`) tìm ra lỗi lớn mà không cần thống kê.
- **So trước/sau** chỉ là định hướng — dễ lẫn yếu tố mùa vụ, khuyến mại, thay đổi quảng cáo; ghi rõ là không phải thử nghiệm có kiểm soát.
- **Cứ làm phiên bản tốt hơn** khi bằng chứng định tính đã rõ và rủi ro thấp.

## Chọn chỉ số

- **Chính:** một chỉ số quan trọng nhất, gắn trực tiếp giả thuyết, dùng để kết luận.
- **Phụ:** giúp diễn giải vì sao/như thế nào.
- **Bảo vệ:** không được xấu đi; dừng nếu xấu đi có ý nghĩa.

Ví dụ trang bảng giá: chính — tỷ lệ chọn gói; phụ — thời gian trên trang, phân bố gói; bảo vệ — yêu cầu hỗ trợ, tỷ lệ hoàn tiền. Với TMĐT COD: bảo vệ — **tỷ lệ đơn hủy/giao không thành công** (một biến thể tăng đặt hàng nhưng tăng hoàn là không thắng).

**Phần tử khách phải chủ động tương tác** (video đầu trang, công cụ tính, khung chat): chỉ một phần nhỏ khách chạm vào, thử trên chuyển đổi tổng sẽ thiếu lực. Hoặc phân tích theo điểm kích hoạt (ghi cùng một điểm kích hoạt ở cả hai nhánh, ví dụ nút phát hiện vào màn hình, và chỉ so khách đã tới đó — không lọc theo lượt bấm vì biến thể có thể đổi ai bấm); hoặc bỏ thử nghiệm, triển khai bản tốt hơn và so theo mức xem hết và chuyển đổi của người xem, gắn mã phiên bản — đây là so sánh định hướng, không phải thử nghiệm có kiểm soát.

## Thiết kế biến thể

| Nhóm | Ví dụ |
|---|---|
| Tiêu đề/nội dung | Góc thông điệp, tuyên bố giá trị, độ cụ thể, giọng |
| Thiết kế | Bố cục, màu, ảnh, phân cấp |
| CTA | Chữ trên nút, kích thước, vị trí, số lượng; nút đặt hàng vs nút nhắn Zalo |
| Nội dung | Thông tin, thứ tự, lượng, bằng chứng xã hội |
| Ưu đãi | Miễn phí ship vs giảm giá, quà tặng, combo (tuân thủ quy định khuyến mại) |

Một thay đổi có ý nghĩa, đủ mạnh để tạo khác biệt, đúng giả thuyết.

## Phân bổ traffic

| Cách | Tỷ lệ | Khi nào |
|---|---|---|
| Chuẩn | 50/50 | Mặc định |
| Thận trọng | 90/10, 80/20 | Giới hạn rủi ro biến thể kém |
| Tăng dần | Bắt đầu nhỏ, tăng | Giảm rủi ro kỹ thuật |

Khách quay lại phải thấy cùng biến thể; cân bằng theo giờ trong ngày/ngày trong tuần.

## Triển khai

- **Phía trình duyệt:** JavaScript sửa trang sau khi tải — nhanh, có thể nhấp nháy. PostHog, Optimizely, VWO.
- **Phía máy chủ:** quyết định biến thể trước khi hiển thị — không nhấp nháy, cần lập trình. PostHog, LaunchDarkly, Split.

## Chạy thử nghiệm

**Trước khi chạy:** [ ] giả thuyết đã ghi; [ ] chỉ số chính đã định; [ ] cỡ mẫu đã tính; [ ] biến thể triển khai đúng; [ ] đo lường đã kiểm tra; [ ] QA trên mọi biến thể, cả điện thoại và trình duyệt trong app Facebook/Zalo.

**Trong khi chạy — làm:** theo dõi lỗi kỹ thuật; kiểm tra chất lượng phân khúc; ghi yếu tố bên ngoài (chiến dịch quảng cáo mới, livestream, khuyến mại, tin tức). **Tránh:** nhìn kết quả rồi dừng sớm; sửa biến thể; thêm nguồn traffic mới.

**Vấn đề nhìn trộm:** xem kết quả trước khi đủ mẫu rồi dừng sớm dẫn tới dương tính giả. Cam kết cỡ mẫu trước.

## Phân tích kết quả

- Với thử nghiệm cố định cỡ mẫu đã định trước, so p-value với mức ý nghĩa đã chọn (thường α = 0,05).
- **p-value** mô tả mức dữ liệu không tương thích với mô hình giả thuyết không: xác suất, **giả định mô hình và các giả thiết của nó đúng**, có kết quả ít nhất cực đoan như quan sát. **Không phải** xác suất kết quả là ngẫu nhiên, giả thuyết không đúng, hay biến thể sẽ lại thắng.
- **Khoảng tin cậy 95%** đến từ một thủ tục bao phủ 95% qua các lần lấy mẫu lặp lại dưới giả thiết của nó — không phải 95% xác suất khoảng cụ thể này chứa hiệu ứng thật. Báo khoảng tin cậy và độ lớn hiệu ứng cùng p-value.
- Dùng phân tích và luật dừng đã định. Thử nghiệm tuần tự và phân tích Bayes có cách diễn giải riêng; đừng dịch điểm "độ tin cậy" của mọi công cụ thành p-value cố định.
- Ý nghĩa thống kê không tự chứng minh giá trị kinh doanh. (Theo [tuyên bố về p-value của Hiệp hội Thống kê Hoa Kỳ](https://www.amstat.org/asa/files/pdfs/p-valuestatement.pdf).)

Tính bằng code từ dữ liệu xuất ra, không đọc nhẩm từ bảng.

**Checklist:** (1) đủ cỡ mẫu chưa — chưa thì là sơ bộ; (2) có ý nghĩa thống kê — xem khoảng tin cậy; (3) độ lớn hiệu ứng có đáng kể — so với mức tối thiểu cần phát hiện, ước tác động; (4) chỉ số phụ có nhất quán; (5) chỉ số bảo vệ có xấu đi; (6) khác biệt theo phân khúc (điện thoại/máy tính, khách mới/cũ).

| Kết quả | Kết luận |
|---|---|
| Thắng có ý nghĩa | Xem độ lớn, độ bất định, chỉ số bảo vệ trước khi triển khai |
| Thua có ý nghĩa | Giữ bản gốc, học vì sao |
| Không khác biệt có ý nghĩa | Báo khoảng hiệu ứng: có thể vẫn cho phép cả lợi và hại đáng kể, hoặc loại trừ hiệu ứng đáng theo đuổi. Theo luật dừng đã định; không kéo dài thử nghiệm đã xong cho tới khi "có ý nghĩa". Lên thử nghiệm mới nếu cần |
| Tín hiệu lẫn lộn | Kiểm chất lượng dữ liệu và chỉ số đã định; phát hiện phân khúc ngoài kế hoạch là khám phá, xác nhận bằng thử nghiệm mới |

## Ghi chép

Mỗi thử nghiệm ghi: giả thuyết; biến thể (kèm ảnh chụp); kết quả (mẫu, chỉ số, ý nghĩa); quyết định và bài học. Mẫu: [references/test-templates.md](references/test-templates.md).

---

## Chương trình thử nghiệm tăng trưởng

**Vòng lặp:** tạo giả thuyết (từ dữ liệu, nghiên cứu khách, đối thủ, phản hồi) → ưu tiên bằng ICE → thiết kế và chạy → phân tích nghiêm ngặt → đưa bản thắng vào playbook → giả thuyết mới từ bài học → lặp lại.

**Nguồn giả thuyết:** phân tích (điểm rơi, trang chuyển đổi thấp); nghiên cứu khách (nỗi đau, bối rối); đối thủ; câu hỏi lặp lại trong chat/hotline/hỗ trợ; bản đồ nhiệt/ghi phiên (do dự, bấm giận dữ, bỏ ngang); thử nghiệm cũ.

**ICE:** chấm 1–10 cho **Tác động** (thành công thì chỉ số chính đổi bao nhiêu), **Tự tin** (dựa trên dữ liệu, không cảm tính), **Dễ** (nhanh và rẻ để làm và đo). Điểm = (T + T + D) / 3. Chạy điểm cao trước; chấm lại hằng tháng.

**Nhịp độ:** 4–8 thử nghiệm/tháng với đa số đội; tỷ lệ thắng 20–30% là phổ biến (cao bền vững có thể do giả thuyết quá an toàn); thời gian trung bình 2–4 tuần; tồn đọng 20+ giả thuyết.

**Playbook khi thắng:**
```
## [Tên thử nghiệm]
Ngày | Giả thuyết | Cỡ mẫu mỗi biến thể
Kết quả: [thắng/thua/không kết luận] — [chỉ số chính] đổi [X%] (KTC 95%: [khoảng], p=[giá trị])
Chỉ số bảo vệ | Khác biệt theo phân khúc
Vì sao thắng/thua | Mẫu dùng lại được | Áp dụng cho | Trạng thái
```

**Nhịp họp:** hằng tuần (30 phút) — kiểm lỗi kỹ thuật và chỉ số bảo vệ, không gọi thắng sớm nhưng dừng nếu bảo vệ xấu đi có ý nghĩa; hai tuần — kết thúc thử nghiệm xong, cập nhật playbook, chạy cái tiếp theo; hằng tháng — nhịp độ, tỷ lệ thắng, mức tăng tích lũy, bổ sung giả thuyết; hằng quý — rà playbook, mẫu thắng nào chưa nhân rộng, phần phễu nào ít được thử.

## Lỗi thường gặp

- **Thiết kế:** thay đổi quá nhỏ; thử quá nhiều thứ; không có giả thuyết; không tính cỡ mẫu với traffic thực tế
- **Thực thi:** dừng sớm; sửa giữa chừng; không kiểm triển khai; chạy vắt qua ngày sale lớn
- **Phân tích:** lờ khoảng tin cậy; chọn phân khúc có lợi; diễn giải quá mức kết quả không kết luận

## Skill liên quan

- `cro` — ý tưởng thử nghiệm theo nguyên tắc tối ưu chuyển đổi
- `analytics` — đo lường thử nghiệm
- `copywriting`, `ad-creative` — nội dung biến thể
- `customer-research` — thử nghiệm định tính
