---
name: emails
description: "Tạo hoặc cải thiện chuỗi email tự động, hoặc khi hỏi nên gửi gì, khi nào, email/chuỗi có hiệu quả không: chào mừng, onboarding, chăm sóc khách tiềm năng, sau mua, kéo khách cũ quay lại, bản tin. Khung chuỗi tin dùng lại được cho Zalo OA. Không văn kiểu AI, không tiêu đề giả 'Re:'. Email tiếp cận lạnh xem cold-email; onboarding trong sản phẩm xem onboarding; tin nhắn SMS xem sms; Zalo xem zalo."
metadata:
  version: 1.0.0
  upstream: emails 2.1.7
---

# Thiết kế chuỗi email

Bạn là chuyên gia email marketing và tự động hóa. Mục tiêu: tạo chuỗi email nuôi dưỡng quan hệ, thúc đẩy hành động và đưa người nhận tới chuyển đổi.

## Điều hướng tài liệu tham khảo (tiếng Anh)

| Ý định | Đọc | Nội dung |
|---|---|---|
| Xây chuỗi chào mừng, chăm sóc, kéo lại, onboarding | [sequence-templates.md](references/sequence-templates.md) | Mục tiêu, nhịp gửi, thứ tự email, hành động chuyển đổi |
| Tìm email vòng đời còn thiếu; kiểm tra onboarding, giữ chân, thanh toán, sử dụng, kéo lại, chiến dịch | [email-types.md](references/email-types.md) | Mục đích, điều kiện kích hoạt, đối tượng, checklist kiểm tra vòng đời |
| Viết/sửa từng email; cải thiện CTA, cá nhân hóa, phân nhóm | [copy-guidelines.md](references/copy-guidelines.md) | Cấu trúc, giọng, độ dài, trường cá nhân hóa, nội dung động, thử nghiệm |

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Đọc mục **Bài học**: góc, ưu đãi, định dạng đã thử thì đừng đề xuất lại như ý mới.

**Bối cảnh Việt Nam:**
- Với khách phổ thông, email thường không phải kênh chính — Zalo OA/ZNS, SMS, Messenger hay có tỷ lệ đọc cao hơn. Thiết kế chuỗi theo **khung tin nhắn**, rồi chọn kênh cho từng tin (xem `zalo`, `sms`). Với B2B, phần mềm, giáo dục, tài chính, email vẫn là kênh quan trọng.
- Email quảng cáo chỉ gửi cho người đã đồng ý, có cách từ chối nhận dễ dàng, gắn nhãn theo quy định (Nghị định 91/2020); dữ liệu email thu thập hợp pháp (Luật BVDLCN 2025). Xem [vn-legal.md](references/vn/vn-legal.md). Thay CAN-SPAM/GDPR trong tài liệu tham khảo bằng quy định Việt Nam.
- Gmail ở Việt Nam hay xếp email marketing vào tab Quảng cáo — nhắc người đăng ký kéo email sang tab Chính trong email chào mừng.
- Viết theo [vn-copywriting.md](references/vn/vn-copywriting.md).

Hiểu rõ:
1. **Loại chuỗi:** chào mừng/onboarding; chăm sóc khách tiềm năng; kéo lại; sau mua; theo sự kiện; giáo dục; bán hàng
2. **Người nhận:** họ là ai; điều gì đưa họ vào chuỗi; họ đã biết/tin gì; quan hệ hiện tại với bạn
3. **Mục tiêu:** chuyển đổi chính; xây quan hệ; phân nhóm; thế nào là thành công

---

## Nguyên tắc

1. **Một email, một việc.** Mỗi email một mục đích chính, một CTA chính.
2. **Giá trị trước, lời mời sau.** Mở bằng điều hữu ích; xây niềm tin bằng nội dung; xứng đáng rồi mới bán.
3. **Liên quan hơn số lượng.** Ít mà tốt thắng nhiều mà nhạt; phân nhóm để liên quan.
4. **Lối đi rõ ràng.** Mỗi email đưa người đọc tới đâu đó; mỗi link làm một việc hữu ích.

## Chiến lược chuỗi

**Độ dài:** chào mừng 3–7 email; chăm sóc khách tiềm năng 5–10; onboarding 5–10; kéo lại 3–5. Phụ thuộc chu kỳ bán, độ phức tạp sản phẩm, giai đoạn quan hệ.

**Nhịp gửi:** chào mừng ngay lập tức; đầu chuỗi cách 1–2 ngày; chăm sóc cách 2–4 ngày; dài hạn hằng tuần hoặc hai tuần một lần. B2B tránh cuối tuần; B2C thử cả cuối tuần. Gửi theo giờ Việt Nam; tránh dịp nghỉ Tết trừ khi là nội dung Tết.

**Tiêu đề:** rõ hơn khéo; cụ thể hơn mơ hồ; dựa trên lợi ích hoặc tò mò; khoảng 40–60 ký tự (tiếng Việt có dấu vẫn tính như ký tự thường, nhưng dễ dài — kiểm hiển thị trên điện thoại); emoji gây chia rẽ, nên thử.

**Mẫu hiệu quả:** câu hỏi ("Vẫn mất 2 tiếng mỗi tối để đối soát đơn?"); hướng dẫn ("Cách [kết quả] trong [thời gian]"); con số ("3 cách để [lợi ích]"); trực tiếp ("Anh Minh ơi, báo cáo tháng 11 đã sẵn sàng"); gợi chuyện ("Sai lầm mình mắc khi [chủ đề]").

**Dòng xem trước:** nối tiếp tiêu đề, khoảng 90–140 ký tự, không lặp tiêu đề, hoàn thiện ý hoặc thêm tò mò.

## Tổng quan các loại chuỗi

### Chào mừng (sau đăng ký) — 5–7 email trong 12–14 ngày
Mục tiêu: kích hoạt, xây niềm tin, chuyển đổi.
1. Chào mừng + trao đúng thứ đã hứa (ngay) — kèm lời nhắc chuyển email sang tab Chính
2. Thắng nhanh (ngày 1–2)
3. Câu chuyện / vì sao chúng tôi làm việc này (ngày 3–4)
4. Bằng chứng xã hội (ngày 5–6)
5. Gỡ một băn khoăn (ngày 7–8)
6. Tính năng/sản phẩm cốt lõi (ngày 9–11)
7. Lời mời chuyển đổi (ngày 12–14)

### Chăm sóc khách tiềm năng (trước khi mua) — 6–8 email trong 2–3 tuần
1. Trao tài liệu + giới thiệu (ngay) 2. Mở rộng chủ đề (ngày 2–3) 3. Đào sâu vấn đề (ngày 4–5) 4. Khung giải pháp (ngày 6–8) 5. Ca khách hàng (ngày 9–11) 6. Điểm khác biệt (ngày 12–14) 7. Xử lý băn khoăn (ngày 15–18) 8. Lời mời trực tiếp (ngày 19–21)

### Kéo lại — 3–4 email trong 2 tuần, kích hoạt sau 30–60 ngày không tương tác
1. Hỏi thăm (thật lòng) 2. Nhắc giá trị (có gì mới) 3. Ưu đãi đặc biệt 4. Lần cuối (ở lại hay hủy nhận tin). Mục tiêu: kéo lại hoặc làm sạch danh sách.

### Onboarding (người dùng sản phẩm) — 5–7 email trong 14 ngày
Phối hợp với onboarding trong sản phẩm — email hỗ trợ, không lặp lại.
1. Chào mừng + bước đầu (ngay) 2. Trợ giúp bắt đầu (ngày 1) 3. Tính năng nổi bật (ngày 2–3) 4. Câu chuyện thành công (ngày 4–5) 5. Hỏi thăm (ngày 7) 6. Mẹo nâng cao (ngày 10–12) 7. Nâng cấp/mở rộng (ngày 14+)

### Sau mua (bán lẻ, TMĐT, dịch vụ)
1. Xác nhận đơn + thời gian giao (ngay) 2. Đang giao (theo trạng thái vận chuyển) 3. Hướng dẫn dùng (sau khi nhận) 4. Hỏi thăm + xin đánh giá (3–7 ngày sau nhận) 5. Gợi ý mua kèm/mua lại đúng chu kỳ. Với khách phổ thông, các tin giao dịch này thường hiệu quả hơn qua Zalo ZNS/SMS.

Mẫu chi tiết: [references/sequence-templates.md](references/sequence-templates.md).

## Các loại email theo nhóm

- **Onboarding:** người dùng mới, khách hàng mới, nhắc bước onboarding quan trọng, lời mời đồng nghiệp
- **Giữ chân:** nâng lên trả phí, nâng gói, xin đánh giá, hỗ trợ chủ động, báo cáo sử dụng, khảo sát NPS, chương trình giới thiệu
- **Thanh toán:** chuyển sang gói năm, thanh toán thất bại, khảo sát khi hủy, nhắc gia hạn
- **Sử dụng:** tóm tắt ngày/tuần/tháng, thông báo sự kiện quan trọng, mốc thành tích
- **Kéo lại:** hết dùng thử, khách đã hủy
- **Chiến dịch:** bản tin hằng tháng, khuyến mại theo mùa (Tết, 11.11, Black Friday…), cập nhật sản phẩm, tin ngành, thay đổi giá

Chi tiết: [references/email-types.md](references/email-types.md).

---

## Viết email

**Cấu trúc:** (1) mở đầu thu hút (2) ngữ cảnh — vì sao điều này quan trọng với họ (3) giá trị (4) CTA (5) lời chào cuối ấm áp, có người thật.

**Trình bày:** đoạn ngắn (1–3 câu); khoảng trắng giữa các phần; gạch đầu dòng để đọc lướt; in đậm tiết chế; ưu tiên điện thoại (phần lớn đọc trên điện thoại).

**Giọng:** trò chuyện, không công văn; ngôi thứ nhất và thứ hai theo xưng hô thương hiệu; chủ động; đọc to lên — nghe có giống người thật không?

### Không văn kiểu AI
Người nhận nhận ra email do máy viết rất nhanh và ngừng đọc. Viết từ điều cụ thể bạn muốn họ biết hoặc làm.
- **Lật ngược đối lập** ("Không chỉ là X, mà là Y") → nói thẳng Y kèm lý do
- **Chuỗi phủ định** ("Không X, không Y, không Z") → nói điều gì xảy ra; một "Không cần thẻ" thì được
- **Đuôi câu chất đống** → dừng ở tuyên bố
- **Tự hỏi tự trả lời** ("Kết quả? Gấp 3.") → nói thẳng
- **Cụm sáo** ("Nói lời tạm biệt với", "Nâng tầm", "Mở khóa")
- **Gạch ngang dài** trong tiêu đề và dòng xem trước; tối đa một hai cái trong email dài

Dấu hiệu riêng của email:
- **Tiêu đề mồi:** "Re:", "Fwd:" giả; "Bạn sẽ không tin…"; "🔥 Tin lớn". Tiêu đề phải đứng vững nếu đó là dòng duy nhất họ đọc.
- **Mở đầu sáo:** "Kính gửi Quý khách, chúng tôi xin trân trọng thông báo…", "Hy vọng anh/chị vẫn khỏe", "Tin vui!". Mở bằng lý do bạn viết.
- **Kết thúc độn:** "Nếu có thắc mắc, đừng ngần ngại liên hệ." Mời một hành động cụ thể, hoặc dừng.

Danh sách đầy đủ: phần văn kiểu AI trong skill `copywriting`.

**Độ dài:** giao dịch 50–125 từ; giáo dục 150–300 từ; kể chuyện 300–500 từ.

**CTA:** nút cho hành động chính, link cho hành động phụ; một CTA chính rõ ràng mỗi email; chữ nút = hành động + kết quả.

Chi tiết về chữ, cá nhân hóa, thử nghiệm: [references/copy-guidelines.md](references/copy-guidelines.md).

---

## Định dạng đầu ra

### Tổng quan chuỗi
```
Tên chuỗi: [Tên]
Điều kiện vào: [Điều gì bắt đầu chuỗi]
Mục tiêu: [Chuyển đổi chính]
Số email: [Số]
Nhịp gửi: [Khoảng cách]
Điều kiện thoát: [Khi nào rời chuỗi — ví dụ đã mua, đã hủy nhận tin]
Kênh: [Email / Zalo / SMS cho từng tin, nếu đa kênh]
```

### Từng email
```
Email [#]: [Tên/Mục đích]
Gửi: [Thời điểm]
Tiêu đề: [Tiêu đề]
Xem trước: [Dòng xem trước]
Nội dung: [Toàn văn]
CTA: [Chữ nút] → [Đích đến]
Phân nhóm/Điều kiện: [Nếu có]
```

### Kế hoạch đo lường
Đo gì và mốc so sánh: tỷ lệ mở (lưu ý số liệu mở bị bóp méo bởi tính năng bảo vệ quyền riêng tư của Apple), tỷ lệ nhấp, tỷ lệ chuyển đổi, tỷ lệ hủy nhận tin, tỷ lệ báo spam, doanh thu mỗi email gửi.

## Câu hỏi theo việc

1. Điều gì đưa người nhận vào chuỗi?
2. Mục tiêu/hành động chuyển đổi chính?
3. Họ đã biết gì về bạn?
4. Họ còn nhận email/tin nào khác từ bạn?
5. Hiệu quả email hiện tại? Danh sách có nguồn đồng ý rõ ràng không?

## Công cụ

Có kết nối (MCP/connector) tới công cụ email thì dùng để soạn nháp và lên lịch (luôn để người dùng duyệt trước khi gửi). Danh mục: [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md) — [Mailchimp](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/mailchimp.md), [Customer.io](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/customer-io.md), [Resend](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/resend.md), [SendGrid](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/sendgrid.md), [Brevo](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/brevo.md), [Kit](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/kit.md). Công cụ email nội địa khác: làm theo cách xuất/nhập của công cụ đó.

## Skill liên quan

- `zalo`, `sms` — các kênh tin nhắn khác trong cùng chuỗi
- `lead-magnets` — tài liệu mở đầu chuỗi chăm sóc
- `churn-prevention` — luồng hủy, ưu đãi giữ chân, thanh toán thất bại
- `onboarding` — onboarding trong sản phẩm (email hỗ trợ)
- `copywriting` — trang mà email dẫn tới
- `ab-testing` — thử nghiệm thành phần email
- `popups` — thu email/số điện thoại
- `revops` — giai đoạn vòng đời kích hoạt chuỗi email
