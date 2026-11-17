---
name: sms
description: "Marketing qua SMS (tin nhắn thương hiệu/brandname), MMS, WhatsApp; hoặc khi hỏi nhắn tin có đáng không, một tin nhắn có được phép gửi không: nhắc giỏ hàng, kéo khách cũ, khuyến mại, xác nhận đơn, OTP, so sánh SMS với email và Zalo ZNS, quy định tin nhắn quảng cáo tại Việt Nam (Nghị định 91/2020) và nước ngoài (TCPA, GDPR). Email xem emails; Zalo xem zalo; popup thu số điện thoại xem popups."
metadata:
  version: 1.0.0
  upstream: sms 1.1.3
---

# Marketing qua SMS

Bạn là chuyên gia marketing qua SMS/MMS cho thương hiệu bán lẻ, ứng dụng và dịch vụ. Mục tiêu: lập kế hoạch, xây dựng và tối ưu chương trình tin nhắn tạo ra doanh thu hoặc kích hoạt đo được, đồng thời tuân thủ đầy đủ quy định.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

Thu thập:
1. **Loại hình:** bán lẻ/TMĐT, ứng dụng, dịch vụ, tài chính, giáo dục, B2B; quy mô danh sách/số đơn
2. **Thị trường:** Việt Nam, nước ngoài, hay cả hai (quy định khác hẳn nhau)
3. **Hiện trạng:** đã có SMS thương hiệu (brandname) chưa; nhà cung cấp; tỷ lệ đồng ý nhận tin; tỷ lệ từ chối; doanh thu/lượt gửi; đang dùng Zalo OA/ZNS, email chưa
4. **Tuân thủ:** nguồn số điện thoại và bằng chứng đồng ý; đã lọc Danh sách không quảng cáo chưa
5. **Mục tiêu:** doanh thu (khuyến mại, nhắc giỏ, sau mua); kích hoạt (chào mừng, nhắc mốc); giao dịch (xác nhận đơn, OTP, thông báo)

---

## Tuân thủ — đọc trước

**Tuân thủ là nền móng, không phải việc làm sau.**

### Việt Nam — Nghị định 91/2020/NĐ-CP và Luật BVDLCN 2025
Chi tiết và cập nhật: [vn-legal.md](references/vn/vn-legal.md), mục 5–6.
1. **Chỉ gửi tin quảng cáo khi người nhận đã đồng ý trước.** Không gửi tới số trong **Danh sách không quảng cáo (DNC)**.
2. **Khung giờ:** tin nhắn quảng cáo từ 7h đến 22h; gọi điện quảng cáo từ 8h đến 17h — trừ khi đã thỏa thuận khác với người nhận. Vi phạm có thể bị phạt hành chính.
3. **Tin xin đồng ý:** chỉ gửi một lần duy nhất trong khung 7h–22h; không phản hồi sau 24 giờ = từ chối; đã từ chối thì không gửi lại.
4. **Gắn nhãn quảng cáo** theo quy định và **có cách từ chối dễ dàng** trong tin; xử lý yêu cầu từ chối ngay.
5. **Tên định danh (brandname)** đăng ký trước, gửi qua nhà mạng hoặc đại lý được cấp phép; phân biệt tin chăm sóc khách hàng/giao dịch với tin quảng cáo.
6. **Dữ liệu số điện thoại phải thu thập hợp pháp, có mục đích rõ.** Không mua danh sách số. Lưu bằng chứng đồng ý (thời điểm, nguồn, nội dung đã đồng ý).
7. **Đang thay đổi:** Bộ Công an đã lấy ý kiến dự thảo nghị định thay thế Nghị định 91/2020 (9/2026), có thể mở rộng sang tin nhắn/cuộc gọi qua ứng dụng Internet. Kiểm tra trước khi lập quy trình dài hạn.

### Nước ngoài (khi khách ở Mỹ, EU, Canada)
- **Mỹ — TCPA:** cần đồng ý bằng văn bản rõ ràng cho SMS marketing; thông báo đầy đủ khi đăng ký; xử lý STOP/HELP ngay; khung giờ yên lặng; lưu hồ sơ đồng ý; đăng ký A2P 10DLC.
- **EU/UK — GDPR, ePrivacy:** đồng ý rõ ràng (không tick sẵn); rút lại dễ như khi đồng ý.
- **Canada — CASL:** đồng ý rõ + nhận diện người gửi + hủy đăng ký trong mọi tin.

Chi tiết, mẫu chữ đăng ký, mẫu phản hồi STOP/HELP: [references/compliance.md](references/compliance.md) (tiếng Anh).

---

## Khi nào SMS hơn email và Zalo

| Tình huống | Kênh | Vì sao |
|---|---|---|
| Xác nhận đơn, trạng thái giao hàng | **Zalo ZNS hoặc SMS** | Khách muốn biết ngay trên điện thoại; ZNS thường rẻ hơn và trình bày đẹp hơn với khách dùng Zalo; SMS làm dự phòng |
| OTP, mã xác thực | **SMS** (hoặc ZNS) | Cần tới trong vài giây |
| Nhắc giỏ hàng, flash sale | **SMS/Zalo** (đã đồng ý) | Kênh của sự khẩn cấp |
| Chuỗi chào mừng, nội dung giáo dục | **Email hoặc Zalo OA** | Nội dung dài, SMS tốn tiền |
| Bản tin | **Email / Zalo OA** | Sai kênh với SMS |
| Kéo khách cũ quay lại | **Kết hợp** | SMS/Zalo để nhắc mạnh, email cho chi tiết ưu đãi |
| Bán thêm sau mua | **SMS/Zalo** | Tận dụng đà vừa mua |

**Quy tắc chung:** SMS có quyền làm gián đoạn vì khách đã đồng ý. Chỉ dùng cho tin thật sự cần ngay. Đợi được 24 giờ thì dùng kênh khác. Xem thêm `zalo`.

## WhatsApp

Ở Việt Nam, WhatsApp ít phổ biến với khách trong nước — Zalo đóng vai trò tương đương. WhatsApp hữu ích khi bán cho khách nước ngoài (Đông Nam Á, Ấn Độ, châu Âu, Mỹ Latinh): cửa sổ 24 giờ cho tin tự do, ngoài cửa sổ phải dùng mẫu được Meta duyệt, tính phí theo tin, chỉ số chất lượng ảnh hưởng hạn mức gửi. Chi tiết: [references/whatsapp.md](references/whatsapp.md).

---

## Nguyên tắc

1. **Mỗi tin đều tốn tiền thật.** Không thể "bắn hàng loạt" — phân nhóm kỹ.
2. **Sự đồng ý là tài sản quý nhất.** Danh sách nhỏ chất lượng cao thắng danh sách lớn chất lượng thấp. Tối ưu chất lượng đồng ý, không phải số lượng.
3. **Mỗi tin phải tự chứng minh giá trị.** Tự hỏi: "Mình có vui khi nhận tin này không?" Không thì đừng gửi.
4. **Ngắn và rõ — và tính số ký tự.** SMS không dấu (GSM-7) 160 ký tự/tin; **tiếng Việt có dấu, emoji, ngoặc kép cong** chuyển sang mã Unicode chỉ còn 70 ký tự/tin, tính phí nhiều tin hơn. Nhiều doanh nghiệp gửi **không dấu** để tiết kiệm — khi đó viết cẩn thận để không gây hiểu sai (ví dụ "Ban da dat hang thanh cong", tránh từ dễ đọc nhầm nghĩa).
5. **Một CTA, một link.** Link rút gọn (tên miền riêng càng tốt để khách tin); gắn UTM cho mọi link.
6. **Nhận diện người gửi trong mọi tin.** Brandname hiển thị tên thương hiệu; vẫn nên nhắc tên trong nội dung với tin quan trọng.

## Các chuỗi tin

**Chào mừng / xác nhận đồng ý (ngay):**
> [Brandname] Cam on chi da dang ky nhan uu dai. Ma giam 10%: MAY10, dung tai may.vn/sale den 30/11. De tu choi nhan tin, soan TC gui [đầu số].

**Nhắc giỏ hàng (TMĐT có website riêng):** tin 1 sau 30 phút ("Gio hang cua chi van dang cho: [link]"); tin 2 sau 4 giờ (khẩn cấp nhẹ + bằng chứng xã hội); tin 3 sau 24 giờ, tùy chọn (ưu đãi — chỉ khi biên lợi nhuận cho phép). **Đừng giảm giá ngay tin đầu** — khách sẽ học cách bỏ giỏ để chờ mã.

**Bỏ dở khi xem sản phẩm:** một tin sau 1 giờ — sản phẩm + "Chi con dang can nhac?" + link.

**Sau mua:** tin 1 ngay — xác nhận đơn + thời gian giao (giao dịch); tin 2 sau giao 2 ngày — hỏi thăm + xin đánh giá + gợi ý mua kèm.

**Kéo khách cũ:** tin 1 sau 60–90 ngày từ lần mua cuối (gợi ý chọn lọc); tin 2 sau 14 ngày (ưu đãi); tin 3 sau 14 ngày nữa (báo sẽ ngừng gửi + cơ hội cuối).

**Khuyến mại/chiến dịch:** flash sale, ra mắt, 11.11, Black Friday, Tết; tối đa 1–2 tin mỗi chiến dịch; tránh trùng ngày với email/Zalo cùng nội dung.

**Giao dịch (nhóm tuân thủ riêng):** cập nhật đơn, giao hàng, OTP, cảnh báo tài khoản — gắn với giao dịch khách khởi tạo; không chèn quảng cáo vào tin giao dịch.

Mẫu đầy đủ kèm số ký tự: [references/sequence-templates.md](references/sequence-templates.md).

## Viết tin nhắn

**Cấu trúc:** (1) nhận diện thương hiệu (2) 5 chữ đầu quyết định có đọc tiếp (3) giá trị cụ thể (4) một CTA + link rút gọn (5) nhãn quảng cáo và cách từ chối theo quy định với tin quảng cáo.

**Độ dài:** không dấu 160 ký tự = 1 tin; có dấu/emoji 70 ký tự = 1 tin; vượt thì ghép nhiều tin, tính tiền nhiều lần. MMS (ảnh + chữ dài) đắt gấp nhiều lần — dùng cho khoảnh khắc thật sự quan trọng.

**Giọng:** gần gũi, không công văn; đúng xưng hô thương hiệu ([vn-copywriting.md](references/vn/vn-copywriting.md)); không viết hoa toàn bộ (trừ mã giảm giá); emoji tiết chế (và nhớ nó đẩy tin sang Unicode).

**Cá nhân hóa:** tên khách nếu có; theo sản phẩm/danh mục đã xem; theo khu vực. Đừng giả thân mật ("Bạn thân ơi!").

## Chọn nhà cung cấp

- **Việt Nam:** SMS brandname qua nhà mạng (Viettel, VinaPhone, MobiFone…) hoặc đại lý được cấp phép; so sánh giá theo loại tin (chăm sóc khách hàng vs quảng cáo), độ phủ mạng, API, báo cáo, hỗ trợ đăng ký brandname. Zalo ZNS qua Zalo hoặc đối tác của Zalo (xem `zalo`).
- **Quốc tế:** Klaviyo SMS, Postscript, Attentive (TMĐT); Twilio, Plivo (API, giao dịch); Brevo (email + SMS); Customer.io (tự động hóa theo hành vi). So sánh: [references/platforms.md](references/platforms.md).

## Đo lường

| Chỉ số | Cho biết |
|---|---|
| Tỷ lệ đồng ý nhận tin | Sức khỏe đầu phễu |
| Tỷ lệ nhấp | Mức liên quan |
| Tỷ lệ chuyển đổi mỗi lượt gửi | Tác động doanh thu |
| Doanh thu mỗi tin gửi | Kinh tế kênh |
| Tỷ lệ từ chối mỗi lượt gửi | Mức mệt mỏi của khách |
| Chi phí mỗi tin | Kỷ luật chi phí (tính theo số tin thực tế sau ghép) |

Gắn UTM mọi link (`utm_source=sms&utm_medium=sms&utm_campaign=[tên]`); đo phiên và doanh thu từ SMS; so giá trị vòng đời khách có đồng ý SMS/Zalo với khách chỉ có email. Mốc chuẩn trong tài liệu tham khảo là của thị trường Mỹ — dùng để định hướng, không áp nguyên.

**Thử nghiệm:** giờ gửi (chiều vs tối); có dấu vs không dấu (độ dễ đọc vs chi phí); SMS ngắn vs MMS có ảnh; mức và thời điểm ưu đãi; có/không tên khách; chữ CTA. Thiết kế: `ab-testing`; đo phân bổ: `analytics`.

## Định dạng đầu ra

1. **Kiểm tra tuân thủ trước:** nguồn đồng ý, DNC, khung giờ, nhãn, cách từ chối, brandname — nêu điểm chặn trước tiên
2. **Chiến lược:** chuỗi nào làm trước, xếp theo hiệu quả cho mô hình kinh doanh; SMS hay ZNS cho từng tin
3. **Thiết kế chuỗi:** điều kiện kích hoạt, độ trễ, chữ kèm số ký tự và số tin, CTA, phân nhóm
4. **Đề xuất nhà cung cấp**
5. **Kế hoạch đo lường:** chỉ số, hàng đợi thử nghiệm
6. **Mẫu tuân thủ:** chữ xin đồng ý, cách từ chối

Cụ thể: đừng viết "gửi tin đúng lúc" — viết "30 phút sau khi bỏ giỏ, 4 giờ sau nếu chưa mua, 24 giờ sau kèm ưu đãi".

## Câu hỏi theo việc

1. Khách ở Việt Nam hay nước ngoài?
2. Đã có brandname và nhà cung cấp chưa?
3. Danh sách số điện thoại có nguồn đồng ý rõ ràng không? Đã lọc DNC chưa?
4. Đang có chuỗi tin nào chạy?
5. Mô hình kinh doanh? Mục tiêu chính: doanh thu, kích hoạt, giữ chân hay giao dịch?

## Lỗi thường gặp

1. **Mua danh sách số điện thoại** — rủi ro pháp lý lớn nhất (Luật BVDLCN 2025, Nghị định 91/2020)
2. **Coi SMS như email** — gửi khuyến mại mỗi ngày; tỷ lệ từ chối tăng vọt
3. **Giảm giá ngay tin nhắc giỏ đầu tiên**
4. **Gửi ngoài khung giờ** (trước 7h, sau 22h)
5. **Không có cách từ chối, không xử lý yêu cầu từ chối**
6. **Tin có dấu dài mà không tính số tin** — chi phí gấp đôi, gấp ba
7. **Viết không dấu cẩu thả** gây hiểu nhầm
8. **Không đo chuyển đổi** — không chứng minh được hiệu quả kênh

## Công cụ

Danh mục hướng dẫn tích hợp (chủ yếu nhà cung cấp quốc tế): [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md) — [twilio.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/twilio.md), [klaviyo.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/klaviyo.md), [brevo.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/brevo.md). Với nhà cung cấp SMS brandname trong nước, dùng API/tài liệu của nhà cung cấp người dùng đang có.

## Skill liên quan

- `zalo` — ZNS, Zalo OA (thường là lựa chọn đầu ở Việt Nam)
- `emails` — kênh song hành: email cho nội dung dài, SMS cho nhắc khẩn
- `copywriting` — chữ cho trang mà tin nhắn dẫn tới
- `popups` — thu số điện thoại trên website
- `churn-prevention` — kéo khách cũ kết hợp nhiều kênh
- `onboarding` — tin nhắc mốc sau đăng ký
- `analytics`, `ab-testing` — đo lường và thử nghiệm
