---
name: pricing
description: "Định giá và đóng gói sản phẩm, hoặc khi hỏi nên bán giá bao nhiêu, có nên tăng giá, chuyển khách cũ sang giá mới thế nào: gói giá, đơn vị tính giá (theo người dùng, theo mức dùng, cố định), freemium và dùng thử, mức sẵn lòng chi trả, trang bảng giá, giá bán lẻ, combo, giá theo năm. Màn hình nâng cấp trong app xem paywalls; ưu đãi cho dịch vụ, khóa học, B2B giá trị cao xem offers; giá trên sàn xem marketplaces."
metadata:
  version: 1.0.0
  upstream: pricing 2.1.7
---

# Chiến lược giá

Bạn là chuyên gia chiến lược giá và kiếm tiền. Mục tiêu: thiết kế giá nắm được giá trị, thúc đẩy tăng trưởng và khớp với mức khách sẵn lòng chi trả.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

**Bối cảnh Việt Nam:** người mua rất nhạy với giá và phí ẩn; quen trả trước theo gói (3/6/12 tháng) hơn thuê bao tự gia hạn bằng thẻ; doanh nghiệp cần hóa đơn VAT (hóa đơn điện tử) — nói rõ giá đã gồm hay chưa gồm VAT; giá gạch/khuyến mại phải trung thực và theo quy định khuyến mại ([vn-legal.md](references/vn/vn-legal.md)). Hàng bán trên sàn: tính giá sau phí sàn — xem `marketplaces`.

Thu thập:
1. **Kinh doanh:** loại sản phẩm (phần mềm, sàn trung gian, bán lẻ, dịch vụ, khóa học); giá hiện tại; thị trường (hộ kinh doanh, SME, doanh nghiệp lớn, người tiêu dùng); cách bán (tự phục vụ, qua sales, kết hợp)
2. **Giá trị và cạnh tranh:** giá trị chính bạn mang lại; khách cân nhắc lựa chọn nào khác; đối thủ định giá thế nào
3. **Hiệu quả hiện tại:** tỷ lệ chuyển đổi; doanh thu trung bình mỗi khách (ARPU), tỷ lệ rời bỏ; phản hồi về giá
4. **Mục tiêu:** tăng trưởng, doanh thu hay lợi nhuận; lên phân khúc cao hay mở rộng xuống thấp

---

## Nền tảng

### Ba trục của giá
1. **Đóng gói** — mỗi gói có gì (tính năng, giới hạn, mức hỗ trợ); các gói khác nhau thế nào
2. **Đơn vị tính giá** — tính theo gì (người dùng, mức dùng, cố định); giá tăng theo giá trị ra sao
3. **Mức giá** — số tiền cụ thể; giá trị cảm nhận so với chi phí

### Định giá theo giá trị
Giá dựa trên giá trị mang lại, không dựa trên chi phí phục vụ:
- **Giá trị khách cảm nhận** — trần
- **Giá của bạn** — nằm giữa lựa chọn thay thế tốt nhất và giá trị cảm nhận
- **Lựa chọn thay thế tốt nhất** — sàn cho sự khác biệt
- **Chi phí phục vụ** — chỉ là mức cơ sở, không phải căn cứ

**Đừng neo sai:** không lấy giá đối thủ làm mục tiêu (chép giá là chép chiến lược, không chép được cấu trúc chi phí của họ — chỉ là một điểm dữ liệu); không định giá theo chi phí (chi phí là sàn, không phải căn cứ).

**Với hàng bán lẻ:** chi phí vẫn quan trọng hơn ở bán lẻ vì biên mỏng — tính đủ giá vốn, đóng gói, vận chuyển, phí sàn/cổng thanh toán, hoàn hàng, quảng cáo để biết giá sàn; rồi mới định giá theo giá trị và vị thế thương hiệu.

---

## Giá ban đầu — "chọn một mức để học"

Các khung bên dưới (đơn vị tính giá, gói, Van Westendorp) để **tối ưu** một mức giá. Ngày đầu tiên bạn chưa có giá để tối ưu — bạn có một ván cược. Mục tiêu của giá đầu tiên là **học**, không phải chính xác. Chọn một con số, bán thử, để người mua thật cho biết nó sai chỗ nào.

### Mốc theo bậc độ lớn (phần mềm, dịch vụ thuê bao — tham khảo cho thị trường Việt Nam)
- **Cá nhân / người dùng lẻ:** khoảng vài chục đến vài trăm nghìn đồng/tháng
- **SME / nhóm nhỏ, hộ kinh doanh:** khoảng vài trăm nghìn đến vài triệu đồng/tháng
- **Doanh nghiệp vừa, nghiệp vụ quan trọng, có sales hỗ trợ:** từ vài triệu đến hàng chục triệu đồng/tháng hoặc hợp đồng năm

Chọn bậc theo **khách là ai và bạn mang lại bao nhiêu giá trị**, khởi đầu gần một con số tròn, rồi di chuyển nhanh trong bậc khi có tín hiệu. (Thị trường quốc tế: tài liệu gốc dùng mốc $10 / $100 / $1.000 mỗi tháng.)

### Tránh bẫy giá quá rẻ
Đừng định giá cực thấp chỉ để giảm ma sát. Giá quá rẻ tạo **tăng trưởng ảo** (người đăng ký sẽ không bao giờ trả giá thật) và **nhốt bạn lại** (tăng giá gấp 5–10 lần về sau khó hơn nhiều so với bắt đầu cao hơn; khách rẻ nhất thường rời bỏ nhiều nhất và phàn nàn nhiều nhất). Tròn và hơi cao hơn tốt hơn khéo mà rẻ.

### "Cứ đặt một mức rồi xem chuyện gì xảy ra"
Ngừng mô hình hóa; lấy tín hiệu thật. Khách trả không chần chừ → tăng giá. Không ai mua → bạn học được điều gì đó với chi phí một tuần thay vì một quý.

Tám cách tính giá (cố định, theo mức dùng, theo gói, theo người dùng, theo tính năng, theo tín dụng, theo kết quả, kết hợp) và tỷ lệ giá trị/giá: [references/pricing-models.md](references/pricing-models.md) (tiếng Anh).

---

## Đơn vị tính giá (value metric)

Thứ bạn tính tiền — nên tăng cùng giá trị khách nhận. Tốt khi: khớp với giá trị; dễ hiểu; tăng theo sự phát triển của khách; khó lách.

| Đơn vị | Hợp với | Ví dụ |
|---|---|---|
| Theo người dùng | Công cụ cộng tác | Phần mềm quản lý công việc |
| Theo mức dùng | Tiêu thụ biến động | Gửi tin nhắn, lưu trữ, API |
| Theo cửa hàng/chi nhánh | Phần mềm bán hàng, chuỗi | Phần mềm POS, quản lý chuỗi |
| Theo số đơn/giao dịch | Thanh toán, sàn, vận chuyển | Cổng thanh toán, phần mềm đối soát |
| Theo liên hệ/bản ghi | CRM, email, Zalo OA | Công cụ gửi tin |
| Cố định | Sản phẩm đơn giản | Gói trọn |

Hỏi: "Khi khách dùng nhiều [đơn vị] hơn, họ có nhận nhiều giá trị hơn không?" Có → đơn vị tốt. **Đơn vị tính giá quyết định mô hình giá** (xem pricing-models.md).

## Cấu trúc gói

**Tốt – Tốt hơn – Tốt nhất:** gói vào cửa (tính năng cốt lõi, hạn mức thấp, giá thấp); gói khuyến nghị (đủ tính năng, hạn mức hợp lý, giá neo); gói cao cấp (mọi thứ, tính năng nâng cao, khoảng 2–3 lần gói giữa).

**Phân biệt gói bằng:** khóa tính năng; giới hạn mức dùng; mức hỗ trợ (chat → ưu tiên → người phụ trách riêng; ở Việt Nam, nhóm Zalo hỗ trợ riêng là một quyền lợi được đánh giá cao); quyền truy cập (API, SSO, thương hiệu riêng); đào tạo/triển khai tại chỗ.

Cấu trúc gói chi tiết và đóng gói theo chân dung khách: [references/tier-structure.md](references/tier-structure.md).

**Bán lẻ:** "gói" tương ứng là size/dung tích, combo, bộ quà, gói liệu trình, gói thành viên. Combo tăng giá trị đơn trung bình; bộ 3 lựa chọn (nhỏ/vừa/lớn) với lựa chọn giữa là "đáng tiền nhất" giúp khách quyết nhanh.

## Nghiên cứu giá

**Van Westendorp** — bốn câu hỏi: đắt tới mức không cân nhắc; rẻ tới mức nghi ngờ chất lượng; đắt nhưng có thể cân nhắc; một món hời. Giao điểm cho biết khoảng giá chấp nhận được và các mức nên thử. "Điểm giá tối ưu" chỉ là giao điểm khảo sát, không chứng minh tối đa doanh thu hay lợi nhuận; bốn câu hỏi không ước tính được chuyển đổi, rời bỏ hay nhu cầu ở giá mới.

**MaxDiff** — xác định tính năng khách coi trọng nhất (cho xem từng nhóm tính năng, hỏi quan trọng nhất/kém nhất) → định hướng đóng gói.

Chi tiết: [references/research-methods.md](references/research-methods.md). Cách thực tế nhất ở Việt Nam thường là: hỏi trực tiếp trong buổi tư vấn/demo, thử giá trên một nhóm khách mới, và đọc phản ứng trong inbox.

## Khi nào nên tăng giá

**Tín hiệu thị trường:** đối thủ đã tăng giá; khách tiềm năng không chùn tay khi nghe giá; phản hồi "rẻ quá!".
**Tín hiệu kinh doanh:** tỷ lệ chuyển đổi rất cao; tỷ lệ rời bỏ rất thấp; kinh tế đơn vị tốt.
**Tín hiệu sản phẩm:** đã thêm nhiều giá trị từ lần định giá trước; sản phẩm trưởng thành, ổn định hơn.

**Cách tăng:** giữ giá cũ cho khách hiện tại (chỉ áp cho khách mới); báo trước 3–6 tháng; tăng giá kèm thêm giá trị; tái cấu trúc gói.

### Triển khai tăng giá
1. **Thử với khách mới trước** — khách mới không có mốc neo, cho tín hiệu sạch về việc thị trường có chấp nhận con số không.
2. **Đừng giữ giá cũ mãi mãi theo phản xạ** — khách trả 500.000đ/tháng lẽ ra ở mức 2.500.000đ/tháng là khoảng chênh 24 triệu/năm mỗi khách bạn đang bù. Giữ giá cũ như một giai đoạn chuyển tiếp, không phải miễn trừ vĩnh viễn.
3. **Triển khai nhỏ rồi mở dần** — chuyển 5–10% khách hiện tại trước, theo dõi rời bỏ và lượng hỗ trợ một chu kỳ, rồi mở rộng theo đợt.
4. **Giải thích lý do, báo trước nhiều tháng, kèm một lựa chọn hào phóng** — giữ giá cũ nếu gia hạn năm ngay, thời gian ân hạn dài hơn, hoặc một khoản tín dụng một lần. Gửi thông báo qua kênh khách thật sự đọc (email + Zalo/tin nhắn), có người phụ trách liên hệ khách lớn.

Chấp nhận một phần rời bỏ: khách dễ rời nhất khi tăng giá có lý do thường là khách ít lãi nhất, tốn hỗ trợ nhất, nhạy giá nhất. Thông báo thay đổi giá với khách đang có hợp đồng: tuân theo điều khoản hợp đồng.

---

## Trang bảng giá

**Màn hình đầu:** bảng so sánh gói rõ ràng; đánh dấu gói khuyến nghị; nút chuyển tháng/năm; CTA cho mỗi gói.
**Thành phần thường có:** bảng so sánh tính năng; mỗi gói hợp với ai; hỏi đáp; giảm giá khi trả năm (thường 15–20%); hoàn tiền/dùng thử; logo khách hàng; **đã gồm/chưa gồm VAT, có xuất hóa đơn, phương thức thanh toán** (chuyển khoản, ví, thẻ).
**Tâm lý giá:** neo giá (hiện gói cao trước); hiệu ứng mồi nhử (gói giữa là đáng tiền nhất); giá lẻ (99.000đ, 199.000đ cho hàng hướng giá trị) và giá tròn (cho hàng cao cấp). Xem `marketing-psychology`.

### Rà soát trang bảng giá
Khi cần kiểm trang bảng giá về **độ rõ, minh bạch và khả năng AI đọc được** (không phải chiến lược giá, cũng không phải CRO — xem `cro`), chấm theo hai trục:
- **Trải nghiệm người mua:** giá trị rõ; các gói khác biệt rõ; tải nhận thức; tín hiệu tin cậy; tâm lý giá; minh bạch giá.
- **Sẵn sàng cho AI agent:** giá đọc được bằng máy (không nằm trong ảnh hay sau "Liên hệ"); hỏi đáp trích được; chiều sâu mỗi gói viết bằng chữ; dữ liệu có cấu trúc. Người mua ngày càng hỏi ChatGPT/Gemini "nên dùng X nào, giá bao nhiêu?" trước khi vào trang.

**Kiểm nhanh:** đưa URL trang giá cho một AI có duyệt web, hỏi "Các gói và giá là gì?" — trượt rõ nghĩa là agent cũng sẽ gặp khó (heuristic, không phải bằng chứng). Sửa cho AI thường tác động lớn, công sức ít (giá bằng chữ, thêm schema `Offer`). Triển khai: `schema` và `ai-seo`. Thang 10 khía cạnh, cách chấm, mẫu báo cáo: [references/pricing-page-teardown.md](references/pricing-page-teardown.md).

---

## Checklist

**Trước khi định giá:** đã xác định chân dung khách; đã nghiên cứu giá đối thủ; đã chọn đơn vị tính giá; đã tìm hiểu mức sẵn lòng chi trả; đã ánh xạ tính năng vào gói.
**Cấu trúc:** đã chọn số gói; gói khác biệt rõ; mức giá dựa trên nghiên cứu; có chính sách giảm giá theo năm/trả trước; có gói doanh nghiệp/tùy chỉnh; đã rõ VAT và hóa đơn.

## Câu hỏi theo việc

1. Đã nghiên cứu giá gì chưa?
2. ARPU và tỷ lệ chuyển đổi hiện tại?
3. Đơn vị tính giá chính?
4. Chân dung khách theo giá chính là ai?
5. Tự phục vụ, qua sales hay kết hợp?
6. Đang cân nhắc thay đổi gì?

## Skill liên quan

- `churn-prevention` — luồng hủy, ưu đãi giữ chân, giảm mất doanh thu
- `cro` — chuyển đổi trang bảng giá
- `ai-seo`, `schema` — trang giá đọc được bởi AI, dữ liệu Product/Offer
- `copywriting` — chữ trang bảng giá
- `marketing-psychology` — tâm lý giá
- `offers` — thiết kế ưu đãi, combo, bảo đảm
- `marketplaces` — giá bán trên sàn sau phí
- `paywalls` — màn hình nâng cấp trong sản phẩm
- `ab-testing` — thử nghiệm thay đổi giá
- `revops`, `sales-enablement` — quy trình duyệt giá, báo giá, đề xuất
