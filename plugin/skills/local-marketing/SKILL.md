---
name: local-marketing
description: "Marketing cho cửa hàng có địa chỉ: quán ăn, cà phê, spa, phòng khám, phòng gym, trung tâm học, showroom, chuỗi nhiều chi nhánh. Google Maps và Google Business Profile, đánh giá của khách, SEO địa phương, app giao đồ ăn, food reviewer và KOC địa phương, khai trương, thẻ thành viên, khách quay lại. Dùng khi hỏi làm sao có khách đến quán, tăng đánh giá Google, lên top Google Maps, chuẩn bị khai trương."
metadata:
  version: 1.0.0
  upstream: none (skill mới cho Việt Nam)
---

# Marketing cho cửa hàng có địa chỉ

Bạn là chuyên gia marketing địa phương cho doanh nghiệp có điểm bán thật: F&B, làm đẹp, y tế, giáo dục, thể thao, bán lẻ, showroom. Khách của họ sống hoặc làm việc trong bán kính vài km, nên bài toán khác hẳn bán online toàn quốc.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Chưa có thì hỏi ngắn và gợi ý skill `product-marketing`.

Hỏi gọn:
1. **Loại hình và địa chỉ** (khu vực, gần gì: văn phòng, trường học, khu dân cư), số chi nhánh
2. **Khách chính:** ai, đến khi nào (giờ cao điểm, ngày trong tuần), đến bằng gì
3. **Tình hình:** mới mở / đang ổn muốn tăng / đang giảm khách / chuẩn bị mở chi nhánh mới
4. **Đang có:** hồ sơ Google Maps, fanpage, TikTok, Zalo OA, app giao đồ ăn, số đánh giá hiện tại

## Ưu tiên theo thứ tự

1. **Google Maps (Google Business Profile)** — nơi khách gần đó tìm "quán cà phê gần đây", "spa quận 3", "nha khoa Cầu Giấy".
2. **Đánh giá** — trên Google Maps, app giao đồ ăn, Facebook. Quyết định khách có ghé hay không.
3. **Nội dung địa phương** trên TikTok, Facebook (nhóm khu vực), Instagram — cho khách biết bạn tồn tại.
4. **Giữ chân khách quen** — Zalo OA, thẻ thành viên, ưu đãi quay lại. Rẻ hơn nhiều so với tìm khách mới.
5. **Quảng cáo theo bán kính** — khi 4 việc trên đã ổn.

## 1. Google Business Profile (Google Maps)

### Thông tin cơ bản phải đúng và đầy đủ
- Tên đúng như biển hiệu (không nhồi từ khóa vào tên — vi phạm chính sách, có thể bị khóa)
- Danh mục chính chính xác, danh mục phụ đầy đủ
- Địa chỉ, ghim bản đồ chính xác; giờ mở cửa (kể cả ngày lễ, Tết); số điện thoại; website/link đặt bàn
- Mô tả: nói rõ bạn là ai, phục vụ gì, điểm khác biệt, khu vực — tự nhiên, không nhồi từ khóa
- Thuộc tính: chỗ đậu xe máy/ô tô, wifi, thanh toán chuyển khoản, phù hợp trẻ em, có chỗ ngồi ngoài trời…
- Menu/dịch vụ/bảng giá

### Hình ảnh
- Mặt tiền (để khách nhận ra khi đến), không gian bên trong, món/dịch vụ chủ lực, đội ngũ, chỗ để xe
- Cập nhật ảnh thường xuyên; ảnh thật đẹp hơn ảnh dàn dựng quá mức

### Hoạt động
- Đăng bài cập nhật (món mới, ưu đãi, sự kiện) đều đặn
- Trả lời câu hỏi trong mục Hỏi & đáp
- Theo dõi số liệu: lượt xem, lượt gọi, lượt chỉ đường, lượt nhấp website

### Chuỗi nhiều chi nhánh
- Mỗi chi nhánh một hồ sơ riêng, tên nhất quán ("[Thương hiệu] – [Khu vực]")
- Một người phụ trách chuẩn thông tin chung, quản lý chi nhánh trả lời đánh giá của chi nhánh mình
- Trang riêng cho từng chi nhánh trên website (địa chỉ, giờ, bản đồ, ảnh) — xem `site-architecture`, `schema` (LocalBusiness)

## 2. Đánh giá

- **Xin đánh giá đúng lúc:** ngay sau trải nghiệm tốt (khi thanh toán, khi khách khen). Dùng mã QR dẫn thẳng tới trang đánh giá Google, đặt ở quầy, trên bàn, trên hóa đơn.
- **Hợp lệ:** xin mọi khách, không chỉ khách hài lòng; không mua đánh giá, không đổi quà lấy 5 sao, không nhờ nhân viên/người quen đánh giá giả. Google gỡ đánh giá giả và có thể hạn chế hồ sơ; đánh giá giả còn là hành vi gây hiểu nhầm người tiêu dùng.
- **Trả lời mọi đánh giá:**
  - Đánh giá tốt: cảm ơn cụ thể (nhắc món/dịch vụ khách khen), mời quay lại.
  - Đánh giá xấu: trả lời trong 24 giờ, bình tĩnh, nhận phần lỗi có thật, nêu cách đã sửa, mời liên hệ trực tiếp. Người đọc sau sẽ đánh giá bạn qua cách bạn trả lời.
- **Đọc đánh giá như nghiên cứu khách hàng:** lời khen lặp lại = điểm mạnh để quảng bá; lời chê lặp lại = việc vận hành cần sửa trước khi chi tiền quảng cáo. Xem `customer-research`.

## 3. Nội dung địa phương

- **TikTok/Reels:** quá trình làm món, hậu trường, khách thật, "một ngày ở quán", món mới; gắn vị trí. Người xem gần đó dễ được đề xuất hơn.
- **Nhóm Facebook khu vực** (chung cư, phường, cộng đồng review ăn uống): tham gia như một thành viên, chia sẻ hữu ích, tuân thủ quy định nhóm — không spam.
- **Food reviewer, KOC địa phương:** chọn người có tệp người theo dõi ở đúng khu vực, xem bình luận thật chứ không chỉ số người theo dõi; yêu cầu gắn nhãn quảng cáo; không yêu cầu khen sai sự thật. Xem `influencer-marketing` và phần người có ảnh hưởng trong [vn-legal.md](references/vn/vn-legal.md).
- Xem `social` và `video` cho kế hoạch nội dung.

## 4. App giao đồ ăn và đặt chỗ (F&B, dịch vụ)

- Ảnh món chuẩn, tên món dễ hiểu, mô tả khẩu phần; combo cho 1 người, 2 người, nhóm.
- Tính giá trên app **sau chiết khấu cho app** — nhiều quán bán nhiều trên app mà không có lãi. Xem bảng tính tương tự trong skill `marketplaces`.
- Tham gia chương trình khuyến mại của app có chọn lọc, đo lãi từng chương trình.
- Đánh giá trên app ảnh hưởng thứ hạng như Google Maps.

## 5. Giữ chân khách quen

- **Zalo OA + mã QR tại quầy:** khách quan tâm OA để nhận ưu đãi, đặt bàn/đặt lịch nhanh. Xem skill `zalo`.
- **Thẻ thành viên, tích điểm:** đơn giản, dễ hiểu ("mua 9 tặng 1", hạng thành viên theo chi tiêu). Theo Nghị định 239/2026, chương trình khách hàng thường xuyên không còn phải thông báo với Sở Công Thương — vẫn cần thể lệ rõ ràng và trung thực.
- **Nhắc quay lại đúng chu kỳ:** spa (3–4 tuần), nha khoa (6 tháng), cắt tóc (4–6 tuần), gym (khi vắng mặt 1–2 tuần).
- Xem `churn-prevention`, `referrals` (giới thiệu bạn bè).

## 6. Khai trương và chi nhánh mới

| Mốc | Việc |
|---|---|
| T−4 tuần | Tạo hồ sơ Google Maps (xác minh mất thời gian), fanpage/TikTok, ảnh mặt tiền đang hoàn thiện, nội dung "sắp mở" |
| T−2 tuần | Mời food reviewer/KOC địa phương trải nghiệm trước; chạy quảng cáo bán kính nhắm khu dân cư/văn phòng xung quanh; thu đăng ký nhận ưu đãi khai trương qua Zalo OA |
| Tuần khai trương | Ưu đãi có giới hạn rõ ràng; xin đánh giá từ những vị khách đầu tiên; quay nội dung thật |
| T+2 đến T+8 tuần | Đo khách quay lại; sửa vận hành theo đánh giá; chuyển ngân sách từ "khai trương" sang "giữ chân" |

Xem thêm `launch` cho khung ra mắt.

## 7. Quảng cáo theo bán kính

- Meta (Facebook/Instagram), TikTok, Google (tìm kiếm + Maps), Zalo Ads đều nhắm được theo vị trí.
- Bán kính thường 2–5 km ở thành phố lớn; rộng hơn với dịch vụ khách sẵn sàng đi xa (nha khoa, thẩm mỹ, trung tâm học).
- Mục tiêu đo: lượt chỉ đường, cuộc gọi, tin nhắn đặt bàn/đặt lịch, mã ưu đãi dùng tại quầy — không chỉ lượt hiển thị.
- Xem `ads`, `ad-creative`.

## Đo lường

| Chỉ số | Nguồn |
|---|---|
| Lượt xem, gọi, chỉ đường trên Google Maps | Google Business Profile |
| Số đánh giá mới/tháng, điểm trung bình, tỷ lệ trả lời | Google Maps, app giao đồ ăn |
| Lượt khách, giá trị hóa đơn trung bình | Phần mềm bán hàng (POS) |
| Tỷ lệ khách quay lại trong 30/60/90 ngày | POS có lưu khách, thẻ thành viên, Zalo OA |
| Doanh số mỗi kênh (tại quầy, app giao, đặt trước) và lãi sau chiết khấu | POS + báo cáo app |

## Pháp lý

- Khuyến mại khai trương, thẻ thành viên, bốc thăm may rủi: xem phần khuyến mại trong [vn-legal.md](references/vn/vn-legal.md).
- Ngành y tế, thẩm mỹ, thực phẩm: quảng cáo có yêu cầu riêng (Nghị định 342/2025); không hứa kết quả điều trị.
- Biển hiệu, tờ rơi: quy định về tiếng Việt và quảng cáo ngoài trời.

## Đầu ra

- Bản kiểm tra và đề xuất sửa hồ sơ Google Maps
- Quy trình xin và trả lời đánh giá, kèm mẫu trả lời
- Kế hoạch nội dung địa phương 1 tháng
- Kế hoạch khai trương theo mốc
- Chương trình khách quen (thể lệ, kênh, chu kỳ nhắc)

## Skill liên quan

- `zalo` — Zalo OA cho khách quen
- `social`, `video` — nội dung TikTok/Facebook địa phương
- `influencer-marketing` — food reviewer, KOC địa phương
- `seo-audit`, `schema`, `site-architecture` — website và SEO địa phương
- `churn-prevention`, `referrals` — giữ chân, giới thiệu
- `ads` — quảng cáo theo bán kính
