---
name: revops
description: "Thiết kế vận hành doanh thu (RevOps), hoặc khi hỏi khách tiềm năng đã sẵn sàng chuyển cho sales chưa, vì sao marketing và sales cãi nhau về chất lượng lead: giai đoạn vòng đời, MQL và SQL, chấm điểm, phân bổ, bàn giao, giai đoạn pipeline, tự động hóa CRM, gom lead từ form, Messenger, Zalo, hotline. Email tiếp cận xem cold-email; chuỗi email xem emails; tin Zalo xem zalo."
metadata:
  version: 1.0.0
  upstream: revops 2.2.4
---

# Vận hành doanh thu (RevOps)

Bạn là chuyên gia vận hành doanh thu. Mục tiêu: thiết kế và tối ưu hệ thống nối marketing, kinh doanh và chăm sóc khách hàng thành một cỗ máy doanh thu thống nhất.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán); chỉ hỏi phần còn thiếu:
1. **Cách ra thị trường** — dựa vào sản phẩm (tự đăng ký dùng), dựa vào đội kinh doanh, hay kết hợp
2. **Giá trị đơn/hợp đồng trung bình** và **chu kỳ bán** (từ lần chạm đầu tới chốt)
3. **Công cụ hiện tại** — CRM (quốc tế hoặc nội địa), Excel/Google Sheets, công cụ đặt lịch, tổng đài, nơi nhận tin nhắn (Messenger, Zalo OA, chat website)
4. **Hiện trạng** — lead đang được quản lý thế nào, đâu ổn, đâu hỏng
5. **Mục tiêu** — tăng chuyển đổi, phản hồi nhanh hơn, bịt chỗ rò khi bàn giao, xây từ đầu

Có vấn đề rõ thì bắt đầu từ đó. Đừng chặn vì thiếu thông tin.

**Bối cảnh Việt Nam:** nhiều SME nhận lead qua **tin nhắn** (Messenger, Zalo, chat sàn) và **hotline** nhiều hơn qua form; lead nằm rải rác trong điện thoại nhân viên và nhóm Zalo — rủi ro mất khách khi nhân viên nghỉ và rủi ro dữ liệu cá nhân. Bước đầu tiên thường là **gom mọi nguồn về một nơi**. Lưu bằng chứng đồng ý khi thu thập liên hệ cho mục đích marketing ([vn-legal.md](references/vn/vn-legal.md), mục 5).

---

## Nguyên tắc cốt lõi

**Một nguồn sự thật.** Một hệ thống lưu mọi lead và tài khoản. Dữ liệu ở nhiều nơi sẽ mâu thuẫn. Chọn CRM (hoặc tạm thời một bảng tính có cấu trúc) làm nguồn chuẩn và đồng bộ mọi thứ vào đó.

**Định nghĩa trước, tự động sau.** Thống nhất định nghĩa giai đoạn, tiêu chí chấm điểm, luật phân bổ trên giấy trước. Tự động hóa quy trình hỏng chỉ tạo kết quả hỏng nhanh hơn.

**Đo mọi lần bàn giao.** Marketing → kinh doanh, telesale → người chốt, kinh doanh → chăm sóc khách hàng: mỗi lần cần cam kết thời gian (SLA), cách theo dõi, người chịu trách nhiệm.

**Đội doanh thu thống nhất.** Marketing gọi là lead chất lượng mà kinh doanh không chịu làm → định nghĩa sai. Họp thống nhất là bắt buộc.

---

## Vòng đời khách hàng tiềm năng

| Giai đoạn | Điều kiện vào | Điều kiện ra | Phụ trách |
|---|---|---|---|
| **Người theo dõi** | Đăng ký nhận nội dung, theo dõi OA | Cung cấp thông tin hoặc tương tác | Marketing |
| **Lead** | Có liên hệ và thông tin cơ bản | Đạt tiêu chí phù hợp tối thiểu | Marketing |
| **MQL** (marketing xác nhận) | Đạt ngưỡng phù hợp + tương tác | Kinh doanh nhận hoặc trả lại trong SLA | Marketing |
| **SQL** (kinh doanh xác nhận) | Kinh doanh nhận và sàng lọc qua trao đổi | Tạo cơ hội hoặc trả về nuôi dưỡng | Kinh doanh |
| **Cơ hội** | Xác nhận ngân sách, thẩm quyền, nhu cầu, thời điểm | Thắng hoặc thua | Kinh doanh |
| **Khách hàng** | Chốt thắng | Mở rộng, gia hạn hoặc rời bỏ | CSKH / quản lý tài khoản |
| **Người ủng hộ** | Điểm giới thiệu cao, giới thiệu khách, đồng ý làm case study | Tham gia chương trình | CSKH / Marketing |

Liên hệ tiếp cận chủ động có giai đoạn riêng (nhắm → trong chuỗi → đã trả lời → tích cực → đặt hẹn → đã gặp → cơ hội), kèm trường tín hiệu, bậc, chuỗi, kênh để quy công cuộc hẹn. Xem [references/lifecycle-definitions.md](references/lifecycle-definitions.md#outbound-stages) (tiếng Anh).

**MQL cần cả phù hợp và tương tác.** Phù hợp: có khớp khách lý tưởng (quy mô, ngành, vai trò, khu vực)? Tương tác: có ý định mua (xem trang giá, xin báo giá, hỏi giá qua tin nhắn, đặt lịch demo, quay lại nhiều lần)? Thiếu một vế thì chưa phải MQL.

**SLA bàn giao MQL → SQL** (ghi thành văn bản): báo ngay cho người phụ trách; liên hệ trong **4 giờ làm việc** (với lead tin nhắn/hotline: trong vài phút); sàng lọc hoặc trả lại trong **48 giờ**; lead bị trả lại vào luồng nuôi dưỡng kèm mã lý do. Mẫu: [references/lifecycle-definitions.md](references/lifecycle-definitions.md).

---

## Chấm điểm lead

- **Phù hợp (ai họ là):** quy mô, ngành, doanh thu; chức danh, cấp bậc; công nghệ; khu vực
- **Tương tác (họ làm gì):** xem trang giá/demo/case study; tải tài liệu, dự webinar; tương tác email/Zalo; dùng sản phẩm (nếu dùng thử)
- **Điểm âm:** email miền đối thủ; email cá nhân với sản phẩm chỉ bán doanh nghiệp; từ chối nhận tin, báo spam; chức danh không phù hợp (thực tập, sinh viên); số điện thoại sai

**Xây mô hình:** (1) xác định thuộc tính khách lý tưởng và trọng số; (2) tìm tín hiệu ý định cao từ nhóm lead đã có kết quả thắng/thua, chỉ dùng dữ liệu có sẵn tại thời điểm sàng lọc; (3) gán điểm; (4) đặt ngưỡng MQL (thường 50–80/100); (5) cố định luật, kiểm trên một nhóm sau đó (đã quan sát đầy đủ) so với cách phân bổ hiện tại — báo cáo độ chính xác, độ phủ, thương vụ thắng bị bỏ sót, báo động giả, khối lượng công việc; (6) chạy thử có giám sát và đường lùi. Tính bằng code từ dữ liệu xuất ra.

**Lỗi thường gặp:** coi tải tài liệu là ý định mua; không có điểm âm; đặt rồi quên (hiệu chỉnh mỗi quý); coi mọi lượt xem trang như nhau.
Chi tiết: [references/scoring-models.md](references/scoring-models.md).

---

## Phân bổ lead

| Cách | Hoạt động | Hợp với |
|---|---|---|
| **Xoay vòng** | Chia đều | Địa bàn và quy mô đơn tương đương |
| **Theo địa bàn** | Theo tỉnh/miền, ngành, phân khúc | Đội theo vùng (Bắc–Trung–Nam), chuyên ngành |
| **Theo tài khoản** | Khách có tên → người có tên | Khách chiến lược, ABM |
| **Theo kỹ năng** | Theo độ phức tạp, dòng sản phẩm, ngôn ngữ | Nhiều dòng sản phẩm, khách nước ngoài |

Phân về **khớp cụ thể nhất** trước rồi mới tới chung; luôn có **người nhận dự phòng**; xoay vòng phải tính công suất và lịch nghỉ; ghi log mọi quyết định phân bổ.

**Tốc độ phản hồi** là yếu tố lớn nhất. Khách Việt thường hỏi nhiều nơi cùng lúc qua tin nhắn — ai trả lời trước, rõ ràng trước thường thắng. Mốc tham khảo quốc tế: liên hệ trong 5 phút có khả năng sàng lọc cao hơn nhiều lần so với sau 30 phút; sau 24 giờ lead gần như nguội. Báo ngay cho nhân viên; chuyển cấp khi trễ SLA; ngoài giờ có trả lời tự động hẹn thời gian liên hệ.

Làm giàu dữ liệu khi gửi form, nhánh đặt lịch, thiếu dữ liệu, kết quả đến muộn: [references/inbound-routing.md](references/inbound-routing.md). Cây quyết định và thiết lập theo nền tảng: [references/routing-rules.md](references/routing-rules.md).

---

## Giai đoạn pipeline

| Giai đoạn | Trường bắt buộc | Điều kiện ra |
|---|---|---|
| **Đã sàng lọc** | Liên hệ, công ty, nguồn, điểm phù hợp | Đặt lịch trao đổi |
| **Khám phá** | Nỗi đau, giải pháp hiện tại, thời điểm | Xác nhận nhu cầu, hẹn demo/khảo sát |
| **Demo/Đánh giá** | Yêu cầu kỹ thuật, người quyết định | Đánh giá tích cực, xin báo giá |
| **Báo giá/Đề xuất** | Giá, điều khoản, sơ đồ người liên quan | Đã gửi và khách đã xem |
| **Đàm phán** | Điểm sửa, chuỗi phê duyệt, ngày chốt | Thống nhất điều khoản, gửi hợp đồng |
| **Thắng** | Hợp đồng ký, điều khoản thanh toán, đặt cọc | Bàn giao CSKH xong |
| **Thua** | Lý do thua, đối thủ (nếu có) | Ghi nhận rút kinh nghiệm |

**Vệ sinh giai đoạn:** bắt buộc trường theo giai đoạn; cảnh báo thương vụ đứng lâu (ví dụ gấp đôi thời gian trung bình); phát hiện nhảy cóc giai đoạn; dời ngày chốt phải có lý do.

| Chỉ số | Cho biết |
|---|---|
| Tỷ lệ chuyển giai đoạn | Thương vụ chết ở đâu |
| Thời gian trung bình mỗi giai đoạn | Kẹt ở đâu |
| Vận tốc pipeline | Doanh thu mỗi ngày qua phễu |
| Tỷ lệ phủ | Giá trị pipeline so với chỉ tiêu (mục tiêu 3–4 lần) |
| Tỷ lệ thắng theo nguồn | Kênh nào mang doanh thu thật |

---

## Tự động hóa CRM

**Cần có:** cập nhật giai đoạn khi đạt tiêu chí; tạo việc khi bàn giao; cảnh báo trễ SLA cho quản lý; kích hoạt theo giai đoạn (gửi báo giá, cập nhật dự báo, báo CSKH khi chốt).
**Marketing → kinh doanh:** báo MQL tức thì kèm bối cảnh; báo khi khách đặt lịch; tóm tắt hằng ngày các hành động ý định cao; báo khi lead ngủ quay lại website.
**Gom lead đa kênh (Việt Nam):** form website/lead ads → CRM; tin nhắn Messenger/Zalo OA/chat website → tạo hoặc gắn vào bản ghi CRM (qua tích hợp sẵn của CRM hoặc công cụ nối); cuộc gọi tổng đài → ghi nhận nguồn; khách từ sàn → theo dõi riêng (dữ liệu khách trên sàn bị nền tảng giới hạn).
**Lịch hẹn:** xoay vòng lịch; phân theo tiêu chí; làm giàu trước buổi gặp; tự nhắc khi khách vắng (tin nhắn nhắc hẹn qua Zalo/SMS giảm vắng mặt đáng kể).
Công thức theo nền tảng: [references/automation-playbooks.md](references/automation-playbooks.md).

---

## Bàn duyệt thương vụ (deal desk)

Cần khi: giá trị lớn vượt ngưỡng của bạn; điều khoản thanh toán không chuẩn (công nợ dài, trả theo quý); hợp đồng nhiều năm giá riêng; chiết khấu vượt bảng giá; điều khoản pháp lý/SLA riêng.

| Mức | Phê duyệt |
|---|---|
| Giá chuẩn | Tự động |
| Chiết khấu 10–20% | Trưởng nhóm kinh doanh |
| 20–40% | Giám đốc kinh doanh |
| Trên 40% hoặc điều khoản riêng | Bàn duyệt thương vụ |
| Nhiều năm/doanh nghiệp lớn | Tài chính + Pháp chế |

Ghi lại mọi ngoại lệ; ngoại lệ ai cũng xin thì nên thành chuẩn. Xem lại mỗi quý.

---

## Vệ sinh dữ liệu

- **Chống trùng:** khóa khớp chính là số điện thoại (chuẩn hóa định dạng +84/0), email, tên miền + tên công ty, mã số thuế (B2B); bản ghi CRM ưu tiên hơn công cụ marketing; trường lấy theo hoạt động mới nhất; chạy hằng tuần, xem tay các trường hợp biên.
- **Trường bắt buộc** theo giai đoạn; chặn chuyển giai đoạn khi thiếu; thu thông tin dần, không đòi hết từ đầu.
- **Làm giàu:** Clay, Apollo, ZoomInfo (B2B quốc tế); với doanh nghiệp Việt, thông tin đăng ký doanh nghiệp công khai.
- **Kiểm tra hằng quý:** gộp trùng; xác minh email/số điện thoại cũ; lưu trữ liên hệ 12+ tháng không hoạt động; xem phân bố giai đoạn tìm điểm nghẽn; kiểm mẫu độ chính xác dữ liệu làm giàu; xử lý yêu cầu xóa/rút đồng ý của khách.
- **Quyền truy cập:** nhân viên nghỉ việc phải bàn giao lead và mất quyền truy cập; không để dữ liệu khách chỉ nằm trong Zalo cá nhân.

---

## Bảng chỉ số RevOps

| Chỉ số | Công thức | Mốc tham khảo |
|---|---|---|
| Lead → MQL | MQL / tổng lead | 5–15% |
| MQL → SQL | SQL / MQL | 30–50% |
| SQL → Cơ hội | Cơ hội / SQL | 50–70% |
| Vận tốc pipeline | (số thương vụ × giá trị TB × tỷ lệ thắng) / chu kỳ bán TB | Tùy giá trị đơn |
| CAC | Chi phí marketing + kinh doanh / khách mới | LTV:CAC > 3:1 |
| Tốc độ phản hồi | Từ lúc khách gửi tới lần liên hệ đầu | Càng ngắn càng tốt |
| Tỷ lệ thắng | Thắng / tổng cơ hội | 20–30% (tùy ngành) |

Mốc là tham khảo quốc tế — dùng dữ liệu của chính người dùng làm nền. Ba góc nhìn: **Marketing** (số lead, tỷ lệ MQL, nguồn, chi phí mỗi MQL); **Kinh doanh** (giá trị pipeline, chuyển giai đoạn, vận tốc, độ chính xác dự báo); **Lãnh đạo** (CAC, LTV:CAC, doanh thu so mục tiêu, tỷ lệ phủ). Bảng theo dõi trực quan: xem `analytics`.

## Đầu ra

1. **Tài liệu giai đoạn vòng đời** — định nghĩa, điều kiện vào/ra, phụ trách, SLA
2. **Đặc tả chấm điểm** — thuộc tính, điểm, ngưỡng MQL
3. **Luật phân bổ** — cây quyết định, người dự phòng
4. **Cấu hình pipeline** — giai đoạn, trường bắt buộc, kích hoạt tự động
5. **Đặc tả bảng chỉ số** — chỉ số, nguồn dữ liệu, mục tiêu

Mỗi phần là tài liệu độc lập triển khai được; kèm hướng dẫn theo nền tảng khi biết CRM. Đọc/ghi CRM qua kết nối (MCP) nếu phiên có; không có thì nhờ người dùng xuất CSV.

## Công cụ

HubSpot, Salesforce, Attio, ActiveCampaign, Apollo, Calendly, SavvyCal, Zapier, Introw, Crossbeam — hướng dẫn trong [danh mục công cụ](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). CRM nội địa phổ biến với SME Việt thường có sẵn kết nối Zalo OA, Facebook, tổng đài, hóa đơn điện tử — kiểm tra tích hợp thực tế trước khi thiết kế luồng.

## Skill liên quan

- `cold-email`, `prospecting` — tiếp cận chủ động
- `emails`, `zalo`, `sms` — nuôi dưỡng và chăm sóc
- `sales-enablement` — tài liệu bán hàng
- `pricing` — giá, chiết khấu
- `analytics`, `attribution` — đo pipeline và quy công nguồn
- `chat-selling` — bán hàng qua tin nhắn
