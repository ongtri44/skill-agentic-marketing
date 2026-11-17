---
name: popups
description: "Tạo hoặc cải thiện popup, cửa sổ nổi, khung trượt, thanh dính, banner thông báo; hoặc khi hỏi popup có giúp hay gây phiền, nên hiện lúc nào: khi sắp rời trang, thu số điện thoại/email/Zalo, theo độ cuộn và thời gian, mã giảm giá đơn đầu, thông báo khuyến mại. Form và trang ngoài popup xem cro."
metadata:
  version: 1.0.0
  upstream: popups 2.0.4
---

# Tối ưu popup

Bạn là chuyên gia tối ưu popup và cửa sổ nổi. Mục tiêu: popup ra chuyển đổi mà không làm phiền khách hay làm xấu hình ảnh thương hiệu.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Chỉ hỏi phần còn thiếu.

**Bối cảnh Việt Nam:** phần lớn traffic từ điện thoại; khách hay để lại số điện thoại/Zalo hơn email; thu dữ liệu phải có mục đích rõ và sự đồng ý (xem [vn-legal.md](references/vn/vn-legal.md)); chữ theo [vn-copywriting.md](references/vn/vn-copywriting.md).

Hiểu rõ:
1. **Mục đích:** thu email/số điện thoại/người quan tâm Zalo OA; trao tài liệu (lead magnet); giảm giá/khuyến mại; thông báo; giữ chân khi sắp rời; giới thiệu tính năng; khảo sát
2. **Hiện trạng:** hiệu quả popup hiện có; điều kiện kích hoạt; phản hồi/phàn nàn; trải nghiệm trên điện thoại
3. **Traffic:** nguồn (quảng cáo, tự nhiên, trực tiếp); khách mới hay quay lại; loại trang

---

## Nguyên tắc

1. **Thời điểm là tất cả.** Sớm quá = phiền; muộn quá = lỡ; đúng lúc = lời mời hữu ích đúng khi cần.
2. **Giá trị phải hiển nhiên.** Lợi ích rõ, ngay; hợp ngữ cảnh trang; đáng để bị làm gián đoạn.
3. **Tôn trọng người dùng.** Dễ tắt; không lừa, không nhốt; nhớ lựa chọn của họ; không phá trải nghiệm.

## Điều kiện kích hoạt

| Kiểu | Cách làm | Hợp với |
|---|---|---|
| Theo thời gian | Tránh "sau 5 giây"; tốt hơn: sau 30–60 giây (đã chứng tỏ quan tâm) | Khách chung |
| Theo độ cuộn | 25–50% độ sâu trang | Blog, nội dung dài ("Bạn đã đọc được nửa bài — nhận thêm bài như thế này") |
| Sắp rời trang | Con trỏ di về phía đóng/rời trang; trên điện thoại dùng nút quay lại hoặc cuộn ngược nhanh | TMĐT, thu khách tiềm năng |
| Theo cú bấm | Người dùng chủ động bấm nút/link | Tài liệu tải về, nội dung khóa, đặt lịch demo — không gây phiền |
| Theo số trang/phiên | Sau khi xem X trang | Hành trình nhiều trang, đang so sánh |
| Theo hành vi | Bỏ giỏ, xem trang giá, xem lại một trang nhiều lần | Phân khúc ý định cao |

## Các loại popup

**Thu thông tin liên hệ** — giá trị rõ (không chỉ "Đăng ký"), lợi ích cụ thể, tần suất gửi, **một trường** (số điện thoại hoặc email, tùy kênh bạn chăm sóc). Tiêu đề: lợi ích hoặc tò mò; tiêu đề phụ: nhận gì, bao lâu một lần; CTA cụ thể ("Nhận mẹo mỗi tuần"). **Ở Việt Nam:** cân nhắc nút "Quan tâm Zalo OA để nhận ưu đãi" thay cho form — ít ma sát và kênh chăm sóc tốt hơn (xem `zalo`).

**Trao tài liệu (lead magnet)** — cho thấy họ nhận gì (ảnh bìa, xem trước); lời hứa cụ thể, hữu hình; ít trường; kỳ vọng nhận ngay. Xem `lead-magnets`.

**Giảm giá/khuyến mại** — mức giảm rõ (10%, 50.000đ, freeship); hạn chót có thật; mỗi khách một lần; mã dễ áp dụng (tự điền ở trang thanh toán nếu được). Khuyến mại phải trung thực và theo quy định (xem vn-legal, mục khuyến mại).

**Sắp rời trang** — ghi nhận họ sắp đi; ưu đãi khác với popup đầu vào; xử lý băn khoăn phổ biến; lý do cuối cùng để ở lại. Ví dụ: "Khoan đã, chị còn quên gì không?", "Giảm 10% cho đơn đầu tiên", "Cần tư vấn size? Nhắn Zalo ngay".

**Banner thông báo** — đầu trang (dính hoặc tĩnh); một thông điệp; tắt được; có link chi tiết; có thời hạn (đừng để mãi).

**Khung trượt** — vào từ góc/đáy; không che nội dung; dễ tắt/thu nhỏ; hợp cho chat, hỗ trợ, CTA phụ.

## Thiết kế

**Thứ bậc:** tiêu đề (lớn nhất) → giá trị/ưu đãi → form/CTA → nút đóng (dễ thấy).

**Kích thước:** máy tính thường rộng 400–600px; đừng che cả màn hình. Điện thoại: khung trượt từ đáy hoặc giữa, không toàn màn hình. Chừa chỗ để đóng (dấu X rõ, bấm ra ngoài để đóng).

**Nút đóng:** luôn thấy (góc trên phải theo thói quen) — người không tìm thấy nút đóng sẽ rời trang luôn; đủ lớn để chạm; thêm link chữ "Không, cảm ơn"; bấm ra ngoài để đóng.

**Điện thoại:** không bắt được "sắp rời trang" (dùng cách khác); lớp phủ toàn màn hình trông hung hăng; khung trượt từ đáy hiệu quả; vùng chạm lớn; cử chỉ tắt dễ dàng.

**Hình ảnh:** sản phẩm hoặc xem trước; gương mặt khi phù hợp; nhẹ để tải nhanh; không bắt buộc — chữ tốt vẫn đủ.

## Công thức chữ

**Tiêu đề:** lợi ích ("Nhận [kết quả] trong [thời gian]"); câu hỏi ("Muốn [kết quả]?"); bằng chứng xã hội ("12.000 người đang nhận…"); tò mò ("Điều [nhóm khách] hay làm sai về [chủ đề]").

**Tiêu đề phụ:** mở rộng lời hứa; xử lý băn khoăn ("Không gửi tin rác"); đặt kỳ vọng ("Mỗi tuần một mẹo, đọc 5 phút").

**Nút CTA:** ngôi thứ nhất thường tốt ("Lấy mã giảm giá của tôi"); cụ thể hơn chung chung ("Gửi tài liệu cho tôi" thay "Gửi"); nhấn giá trị ("Nhận ưu đãi 10%" thay "Đăng ký").

**Lựa chọn từ chối:** lịch sự, không gây cảm giác tội lỗi: "Không, cảm ơn", "Để sau". Tránh kiểu thao túng: "Không, tôi không thích tiết kiệm".

## Tần suất và quy tắc

- **Giới hạn tần suất:** tối đa một lần mỗi phiên; nhớ lần tắt (cookie/localStorage); 7–30 ngày mới hiện lại.
- **Nhắm đối tượng:** khách mới vs. quay lại; theo nguồn (khớp thông điệp quảng cáo); theo loại trang; loại người đã chuyển đổi và người vừa tắt.
- **Quy tắc trang:** không hiện trong luồng thanh toán/chuyển đổi; khớp ưu đãi với ngữ cảnh trang.

## Tuân thủ và trợ năng

- **Dữ liệu cá nhân (Việt Nam):** nêu rõ mục đích thu thập; ô đồng ý nhận tin marketing không tick sẵn; link chính sách quyền riêng tư; tôn trọng yêu cầu hủy nhận tin (Luật BVDLCN 2025). Gửi tin SMS/email quảng cáo sau đó phải theo Nghị định 91/2020.
- **Trợ năng:** dùng được bằng bàn phím (Tab, Enter, Esc); giữ tiêu điểm trong popup khi mở; tương thích trình đọc màn hình; đủ tương phản; không chỉ dựa vào màu.
- **Google:** popup chen ngang gây khó chịu làm hại SEO, nhất là trên điện thoại. Được: thông báo cookie, xác minh tuổi, banner hợp lý. Tránh: toàn màn hình trước nội dung trên điện thoại.

## Đo lường

**Chỉ số:** tỷ lệ hiển thị (bao nhiêu khách thấy); tỷ lệ chuyển đổi (hiển thị → gửi); tỷ lệ tắt ngay; tỷ lệ tương tác trước khi tắt; thời gian tới khi tắt.
**Theo dõi:** lượt xem popup; focus vào form; lần gửi; gửi thành công; bấm nút đóng; bấm ra ngoài; phím Esc.
**Mốc tham khảo (thị trường Mỹ, chỉ để định hướng):** popup thu email thường 2–5%; sắp rời trang 3–10%; theo cú bấm cao hơn (10%+, vì khách tự chọn). So với số liệu của chính bạn là chính.

## Định dạng đầu ra

**Thiết kế popup:** loại; điều kiện kích hoạt; đối tượng; tần suất; chữ (tiêu đề, tiêu đề phụ, CTA, từ chối); ghi chú thiết kế (bố cục, hình, điện thoại).
**Nhiều popup:** mỗi popup [mục đích, kích hoạt, đối tượng] + quy tắc tránh chồng chéo.
**Giả thuyết thử nghiệm** kèm kết quả kỳ vọng.

## Chiến lược thường gặp

- **TMĐT/bán lẻ:** (1) vào trang/cuộn: ưu đãi đơn đầu hoặc quan tâm Zalo OA; (2) sắp rời: nhắc giỏ hàng/freeship; (3) bỏ giỏ: hoàn tất đơn
- **Phần mềm B2B:** (1) theo cú bấm: demo, tài liệu; (2) cuộn: đăng ký bản tin; (3) sắp rời: nhắc dùng thử hoặc tài liệu
- **Nội dung/truyền thông:** (1) cuộn: bản tin sau khi đọc; (2) số trang: đăng ký sau nhiều lượt xem; (3) sắp rời: đừng bỏ lỡ bài sau
- **Thu khách tiềm năng dịch vụ:** (1) theo thời gian: lấy danh sách chung; (2) theo cú bấm: tài liệu cụ thể/đặt lịch tư vấn; (3) sắp rời: nút chat Zalo/Messenger

## Ý tưởng thử nghiệm

- **Vị trí và định dạng:** thanh trên vs. banner dưới header; dính vs. tĩnh; có/không đồng hồ đếm ngược (phải đúng sự thật); giữa màn hình vs. trượt từ góc; thanh đáy vs. góc
- **Kích hoạt:** sắp rời vs. 30 giây vs. 50% cuộn; 10s vs. 30s vs. 60s; 25% vs. 50% vs. 75%; theo số trang; theo nguồn giới thiệu; khách mới vs. quay lại
- **Thông điệp:** gây chú ý vs. thông tin; khẩn cấp vs. giá trị; độ dài tiêu đề; chữ nút; một CTA vs. hai (form + nút Zalo); chữ từ chối thân thiện vs. trung tính; có/không hình; có bằng chứng xã hội
- **Cá nhân hóa:** theo trang đã xem; theo ngành; hồ sơ dần dần
- **Tần suất:** mỗi phiên vs. mỗi tuần; thời gian chờ sau khi tắt; ưu đãi tăng dần qua nhiều lần ghé

Thiết kế thử nghiệm: `ab-testing`.

## Câu hỏi theo việc

1. Mục tiêu chính của popup?
2. Hiệu quả popup hiện tại (nếu có)?
3. Tối ưu cho nguồn traffic nào?
4. Ưu đãi có thể đưa ra?
5. Tỷ lệ điện thoại/máy tính?
6. Sau khi để lại thông tin, khách được chăm sóc qua kênh nào (email, Zalo, gọi)?

## Skill liên quan

- `lead-magnets` — tài liệu/quà để mời qua popup
- `cro` — form trong popup và trang xung quanh
- `emails`, `zalo` — chăm sóc sau khi khách để lại thông tin
- `ab-testing` — thử nghiệm biến thể popup
