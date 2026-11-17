---
name: attribution
description: "Xác định hoạt động marketing nào thực sự mang doanh thu, hoặc khi hỏi kênh này có hiệu quả thật không, tin số nào, ghi công podcast, KOL, chia sẻ qua Zalo, Messenger thế nào: mô hình quy công, nền tảng nhận vơ, xem TikTok mua trên Shopee, MMM, thử nghiệm tăng trưởng thật, hỏi khách biết qua đâu. UTM và đo lường xem analytics; pixel và CAPI xem conversion-tracking; doanh thu CRM xem revops; tìm kiếm AI xem ai-seo."
metadata:
  version: 1.0.0
  upstream: attribution 1.1.9
---

# Quy công (attribution)

Bạn giúp người dùng trả lời câu hỏi khó nhất trong marketing: **nỗ lực nào thực sự tạo ra chuyển đổi và doanh thu này?** Đây là nơi tiền bị mất nhiều nhất — vào kênh trông đẹp ở bảng này, tệ ở bảng kia; vào "trực tiếp" và "tìm kiếm thương hiệu" che giấu nguồn thật; vào mô hình âm thầm biến một quan điểm thành "sự thật".

Hai trụ cột — xác định người dùng cần cái nào:
- **(A) Diễn giải** — chọn mô hình, chọn cách đo, **đối chiếu các con số mâu thuẫn**. Áp dụng cho mọi người, không cần kỹ thuật.
- **(B) Tự sở hữu quy công (dữ liệu bên thứ nhất)** — tự gắn và nối dữ liệu khi kiểm soát website/app; đặc biệt khi chuyển đổi xảy ra trên miền không phải của mình.

Phần lớn bắt đầu từ (A). Đọc Hồ sơ marketing trước (`.agents/product-marketing.md`, kiến thức của Project) — loại hình kinh doanh, chu kỳ bán, chuyển đổi chính quyết định gần như mọi khuyến nghị.

**Bối cảnh Việt Nam đặc biệt khó quy công:**
- **Xem một nơi, mua nơi khác:** xem video TikTok/Facebook → tìm và mua trên Shopee/Lazada, nhắn Zalo, hoặc ra cửa hàng. Không nền tảng nào thấy trọn hành trình.
- **Chia sẻ ngầm (dark social) cực lớn:** link và ảnh chụp gửi qua Zalo, Messenger, nhóm Facebook — không có referrer.
- **Đơn qua tin nhắn và hotline** không đi qua website.
- **COD:** "đặt hàng" ≠ "doanh thu" — nguồn sự thật nên là **đơn giao thành công** trong hệ thống quản lý đơn/POS.

## Ranh giới

- Theo dõi sự kiện, UTM, GA4/GTM → `analytics` (quy công giả định đã có đo lường)
- Pixel, CAPI, đo chuyển đổi phía máy chủ → `conversion-tracking`
- Giai đoạn pipeline, vòng đời lead, doanh thu CRM → `revops`
- Hiện diện và đo trên tìm kiếm AI → `ai-seo`

---

## Trụ cột A — Diễn giải

### 1. Quy công cho biết gì và không cho biết gì
- **Định hướng, không phải sự thật.** Là mô hình nhân quả từ dữ liệu không đầy đủ (cookie hết hạn, phiên đứt, chạm offline biến mất, nghiên cứu trên điện thoại mua trên máy tính). Coi là gợi ý mạnh, không phải phán quyết.
- **Mỗi mô hình là một quan điểm.** First-touch và last-touch sai theo hai hướng ngược nhau. Chọn mô hình là chọn tin câu chuyện của ai — nói rõ.
- **Khoảng chênh là bình thường — tách kết quả khỏi công.** Tổng chuyển đổi các nền tảng tự báo hầu như luôn vượt chuyển đổi thật, vì nền tảng nào cũng nhận cùng một đơn theo cửa sổ của mình. Đếm chuyển đổi thật **một lần**, khử trùng với một nguồn sự thật; giải thích công của nền tảng riêng. Hai thứ không khớp nhau, và phân bổ mô hình hóa không bao giờ thay sổ chuyển đổi.

Khi người dùng đòi "một con số đúng": "Mình có thể đưa con số **nhất quán, bảo vệ được** và đọc được kênh nào đang đi lên. Một sự thật khách quan duy nhất không tồn tại — đây là lý do, và đây là cách vẫn ra quyết định được."

### 2. Mô hình quy công

| Mô hình | Luật chia công | Hợp với | Sai ở đâu |
|---|---|---|---|
| **First-touch** | 100% cho chạm đầu | Định giá đầu phễu; chu kỳ ngắn | Bỏ qua thứ chốt đơn; thổi phồng kênh nhận diện |
| **Last-touch** | 100% cho chạm cuối | Phản hồi trực tiếp, TMĐT nhanh | Thổi phồng cuối phễu, tìm kiếm thương hiệu, trực tiếp |
| **Last non-direct** | Chạm cuối, bỏ qua "trực tiếp" | Sửa rẻ cho ô "trực tiếp" | Vẫn một chạm; chỉ dời điểm mù |
| **Tuyến tính** | Chia đều | Hành trình dài, nhiều bước | Coi lượt ghé vội như buổi demo |
| **Suy giảm theo thời gian** | Gần chuyển đổi được nhiều hơn | Chu kỳ dài, độ gần quan trọng | Thiệt đầu phễu; vẫn là giả định |
| **Theo vị trí (chữ U)** | 40% đầu, 40% cuối, 20% giữa | B2B có khoảnh khắc "tạo" và "chốt" rõ | Tỷ lệ 40/40/20 tùy tiện |
| **Dựa trên dữ liệu** | Theo đóng góp biên mô hình hóa | Tài khoản khối lượng lớn | Hộp đen; cần khối lượng; không thấy chạm offline/ngầm |

**Lưu ý nền tảng:** Google Ads và GA4 đã bỏ first-click, tuyến tính, suy giảm, theo vị trí khỏi lựa chọn báo cáo (2023); chỉ còn **dựa trên dữ liệu** và **last-click**. Dạy cả bảng như **khái niệm** và mô hình tự tính được trên dữ liệu sự kiện/CRM/kho dữ liệu của mình.

**Quy tắc:** chu kỳ dài thì không báo một mô hình đơn lẻ — đặt **first-touch và last-touch cạnh nhau**, khoảng cách giữa chúng chính là nhận định. Mô hình dựa trên dữ liệu cần khối lượng (Google khuyến nghị ~200 chuyển đổi và ~2.000 tương tác quảng cáo trong 30 ngày); ít hơn thì thường gần bằng last-click. Mô hình ít quan trọng hơn **sự nhất quán** cộng một phép kiểm ngoài mô hình (khảo sát tự báo, mục 4). Toán và ví dụ: [references/attribution-models.md](references/attribution-models.md) (tiếng Anh).

### 3. Ba hệ phương pháp đo

| Phương pháp | Là gì | Trả lời | Cần | Lưu ý |
|---|---|---|---|---|
| **MTA** (quy công đa chạm) | Nối chạm cấp người dùng, áp mô hình | "Chạm nào xuất hiện trên hành trình chuyển đổi?" | Theo dõi sạch, xuyên thiết bị | Mất cookie và quyền riêng tư làm rỗng dữ liệu; thiên về tìm kiếm/trực tiếp |
| **MMM** (mô hình hỗn hợp marketing) | Hồi quy chi tiêu vs kết quả theo thời gian | "Đóng góp tổng của từng kênh, kể cả offline/thương hiệu?" | 2–3 năm dữ liệu tuần, chi tiêu có biến động | Tương quan; chậm; cần ngân sách thay đổi thật |
| **Tăng trưởng thật** (giữ lại theo vùng, bật/tắt) | Thí nghiệm có kiểm soát | "Kênh này có **gây ra** mức tăng mà không có nó thì không có?" | Khả năng giữ lại; đủ khối lượng | Chuẩn vàng, nhưng mỗi lúc chỉ thử được vài thứ |

**Chọn:** ngân sách nhỏ/chu kỳ ngắn → UTM tốt + last non-direct + **hỏi khách biết qua đâu** hơn mô hình cầu kỳ. Ngân sách vừa, nhiều kênh → MTA hằng ngày + thử nghiệm tăng trưởng thật định kỳ cho khoản chi lớn nhất. Ngân sách lớn có offline/thương hiệu → MMM cho danh mục + thử nghiệm để kiểm hệ số. Thử nghiệm tăng trưởng thật là trọng tài khi hai kênh cùng nhận một chuyển đổi. Ở Việt Nam, thử **giữ lại theo tỉnh/thành** (tắt kênh ở một số tỉnh tương đồng) là cách khả thi với nhiều doanh nghiệp. Bảng quyết định và cách đọc kết quả: [references/measurement-paradigms.md](references/measurement-paradigms.md).

### 4. Khách tự báo ("Anh/chị biết tới chúng tôi qua đâu?")

Tín hiệu bị dùng ít nhất và thường trung thực nhất với chu kỳ dài và chia sẻ ngầm: bắt được thứ theo dõi không thể thấy — KOL, podcast, nhóm Facebook, bạn bè gửi qua Zalo, "đi ngang qua cửa hàng".
- **Hỏi ngay lúc chuyển đổi** (đăng ký, mua đầu, đặt lịch, chốt đơn qua chat): trí nhớ còn tốt. Với bán qua tin nhắn/hotline: **nhân viên hỏi và ghi vào trường nguồn** trong CRM/phần mềm bán hàng — đây là dữ liệu quy công quý nhất của nhiều SME Việt.
- **Cách hỏi:** danh sách kênh đã biết **+ ô "khác/kể thêm"**. Câu mở bắt chia sẻ ngầm tốt hơn; danh sách dễ đếm hơn nhưng dẫn dắt.
- **Là đầu vào tam giác hóa, không phải chân lý:** người ta nhớ chạm **ấn tượng**, không phải chạm đầu. **Chiết khấu khi biến thành công** — 22% nhớ tới TikTok là bằng chứng nhận diện, không phải TikTok xứng 22% chuyển đổi.

### 5. Đối chiếu nguồn mâu thuẫn

"Google báo 50, Meta 40, GA 60, CRM 35 — ai đúng?" Không ai cả.

| Nguồn | Thiên về | Vì |
|---|---|---|
| **Nền tảng quảng cáo** (Google, Meta, TikTok) | Đếm thừa cho chính mình | Nhận cả xem lẫn bấm trong cửa sổ riêng; cùng một đơn nhiều nền tảng nhận; Meta không trừ đơn hoàn/COD thất bại |
| **GA/phân tích web** | Last non-direct | Mất xuyên thiết bị, mất người chặn cookie, đổ cái không biết vào "trực tiếp"; không thấy đơn qua chat/sàn |
| **Sàn TMĐT** | Quy công trong sàn | Không thấy chạm ngoài sàn đã đưa khách vào |
| **CRM/phần mềm bán hàng** | Thứ nhân viên nhập | Nhập tay, ghi đè nguồn, đơn offline không dấu vết số |
| **Khách tự báo** | Chạm đáng nhớ | Thiên lệch trí nhớ; thiếu chạm nhàm chán nhưng thật (remarketing) |

**Cách tam giác hóa:**
1. **Một nguồn sự thật cho số chuyển đổi** — thường là CRM/hệ thống đơn (nơi tiền là thật; với COD: đơn giao thành công). Nguồn khác chỉ giải thích **từ đâu**, không định nghĩa lại **bao nhiêu**.
2. **Không cộng các nền tảng.** Google và Meta cùng nhận một đơn = một đơn hai người nhận.
3. **Đọc xu hướng đồng thuận, không đòi khớp tuyệt đối.**
4. **Khách tự báo làm trọng tài** khi nền tảng tranh nhau; **thử nghiệm tăng trưởng thật** khi đáng. **Không** biến khoảng chênh nền tảng–GA thành hệ số ("Meta nhận gấp đôi GA" ≠ "nhân đôi Meta") — điều tra cửa sổ và lượt xem, rồi dựa ghi đè vào thử nghiệm.
5. **Chấp nhận và ghi rõ khoảng chênh:** "Nền tảng nhận N; xác minh được M; phần chênh là nhận vơ + lượt xem + không theo dõi được — đây là phân bổ tốt nhất."
6. **Biến tam giác hóa thành luật khi có thể** — khi đã có kết quả thử nghiệm hoặc dải khảo sát tin cậy cho một kênh, áp **ghi đè cấp kênh** có ghi chép trên báo cáo. Chi tiết: [measurement-paradigms.md](references/measurement-paradigms.md).

Đầu ra là phân bổ trung thực kèm mức tin cậy, không phải đối chiếu giả tới số lẻ. Mọi phép tính làm bằng code từ dữ liệu xuất ra, trên cùng cửa sổ thời gian đã khép.

### 6. Điểm mù

- **Trực tiếp** — ngăn kéo tạp: gõ địa chỉ, bookmark, nhưng cả referrer bị mất, từ app sang web, chia sẻ ngầm, chạm bị rơi. Xem thành phần trước khi coi là lỗi đo.
- **Tìm kiếm thương hiệu** — người biết bạn ở nơi khác rồi Google tên bạn. Tách thương hiệu/không thương hiệu, nếu không sẽ cắt nhầm ngân sách đầu phễu.
- **Chia sẻ ngầm** — Zalo, Messenger, nhóm Facebook, podcast, ảnh chụp màn hình. Chỉ khách tự báo thấy được.
- **Xuyên nền tảng** — xem TikTok/KOL mua Shopee; theo dõi tăng tìm kiếm tên shop/sản phẩm trên sàn và doanh số sàn trong cửa sổ chiến dịch.
- **Trợ lý AI** — tác động rồi đưa khách qua tìm kiếm thương hiệu/trực tiếp. Chuyên sâu: `ai-seo`.

Khi trực tiếp và tìm kiếm thương hiệu áp đảo, giải thích phổ biến nhất là đầu phễu đang chạy tốt nhưng bị che. Xác nhận trước khi kết luận: loại khách cũ, referrer mất, khám phá offline; rồi xem khách tự báo hoặc chạy thử nghiệm. Nói rõ bằng chứng ủng hộ hướng nào.

### 7. Theo loại hình

- **B2B (chu kỳ dài, có sales):** CRM là nguồn sự thật; first-touch + theo vị trí cạnh nhau; hỏi nguồn khi đặt demo/ký; doanh thu pipeline là bảng điểm thật (`revops`). Chạm offline (sự kiện, gặp mặt, người quen giới thiệu) làm MTA yếu nhất, khách tự báo mạnh nhất.
- **TMĐT/D2C (chu kỳ ngắn):** dựa vào ROAS nền tảng nhưng **không tin hẳn** (thổi phồng, COD hoàn); kiểm bằng MMM khi chi tiêu đủ lớn và thử nghiệm tăng trưởng thật cho kênh lớn nhất; khảo sát sau mua. Last-touch chấp nhận được cho hàng mua nhanh.
- **Bán đa kênh (website + sàn + chat + cửa hàng):** gom đơn mọi kênh về một phần mềm bán hàng/POS; trường nguồn bắt buộc khi tạo đơn; báo cáo tổng doanh thu theo tuần so với chi tiêu marketing tổng (MER) làm thước đo nền.
- **Dịch vụ địa phương:** cuộc gọi, tin nhắn, đặt lịch; số điện thoại/link riêng theo kênh; hỏi khách tại quầy.
Playbook đầy đủ: [references/by-business-type.md](references/by-business-type.md).

---

## Trụ cột B — Tự sở hữu quy công

Khi người dùng **kiểm soát website/app** và muốn tự gắn — đặc biệt khi chuyển đổi xảy ra **trên miền của bên khác** (công cụ đặt lịch, trang thanh toán hosted). Runbook kèm mẫu mã: [references/first-party-tracking.md](references/first-party-tracking.md).

**Đồ thị định danh:** khách vào ẩn danh → công cụ phân tích gán `distinct_id` ẩn danh và đóng dấu thuộc tính chạm đầu (`$initial_referrer`, `$initial_utm_*`) → tại chuyển đổi gọi **`identify()`** với mã ổn định (mã người dùng nội bộ) → lịch sử ẩn danh **gộp** vào người đã biết → mọi chuyển đổi chia được theo kênh chạm đầu.

**Lỗ hổng `identify()`:** lỗi phổ biến nhất — không gì gọi `identify()`, khách hàng nào cũng như từ trên trời rơi xuống. Kiểm trước (nhiều app đã identify khi đăng ký), chỉ vá các chuyển đổi chưa gắn.

**Nối chuyển đổi trên miền bên thứ ba:** (1) khi bấm, bộ trang trí link gắn `distinct_id` ẩn danh vào URL đi ra qua **metadata passthrough** của công cụ; (2) công cụ lưu và trả lại trong **webhook**; (3) bộ xử lý webhook gộp định danh + bắn sự kiện chuyển đổi.

**Hàng rào (không bỏ qua):**
- **Chỉ truyền mã ẩn danh — đóng khi nghi ngờ.** Sau `identify()`, mã hiện tại là email/UUID; rò vào URL bên thứ ba hoặc gộp theo nó làm hỏng hồ sơ. Từ chối mã giống dữ liệu cá nhân (chứa `@`), giới hạn độ dài; không chắc thì **không gửi gì**.
- **Chất lượng chạm đầu:** loại referrer đăng nhập/thanh toán (`accounts.google.com`, cổng thanh toán), tên miền con của chính mình, máy dev khỏi phân loại referrer.
- **Nối xuyên tên miền con:** website → app trên tên miền con phải chung một dự án phân tích + cookie xuyên tên miền con. Chờ số gần bằng 0 tới khi xác minh được trên production.
- **Dữ liệu cá nhân:** định danh người dùng là xử lý dữ liệu cá nhân — tuân thủ Luật BVDLCN 2025 ([vn-legal.md](references/vn/vn-legal.md), mục 5).

**Báo cáo và chặng cuối:** chuyển đổi chia theo kênh chạm đầu → nối doanh thu: **kênh → chuyển đổi → doanh thu**. Lưu **toàn bộ chuỗi chạm** để tự tính mô hình đa chạm. Ghi kết quả vào CRM: trường `nguồn` kèm `độ tin` và `căn cứ` (nối hành trình / khách tự báo / ước theo cửa sổ chiến dịch), đọc Trả phí vs Tự nhiên từ medium, gộp lên cấp tài khoản (B2B). Mẫu áp dụng cho PostHog, Segment, Amplitude, GA4 (user-id).

---

## Đầu ra: bản đọc quy công

```markdown
# Bản đọc quy công — [ngày]
## Câu hỏi
[Quyết định cần đưa ra — ví dụ: "quý sau dồn ngân sách vào đâu?"]
## Nguồn sự thật
[Hệ thống định nghĩa số chuyển đổi, vì sao]
## Mỗi nguồn nói gì
| Kênh | Nền tảng báo | GA | CRM/đơn hàng | Khách tự báo | Nhận định của ta |
[Khử trùng với nguồn sự thật; không cộng dồn]
## So sánh mô hình (chu kỳ dài)
[First-touch vs last-touch cạnh nhau]
## Độ tin và khoảng trống
[Khoảng chênh, điểm mù, điều không thấy được]
## Khuyến nghị
[Phân bổ kèm mức tin cậy; thử nghiệm trọng tài nên chạy]
```

## Công cụ

PostHog, GA4 (có MCP), Dub (link ngắn + quy công click), Segment, HubSpot, Salesforce, Supermetrics (gom số liệu nền tảng), RB2B — hướng dẫn trong [danh mục công cụ](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Không có kết nối thì nhờ người dùng xuất CSV từ từng nền tảng, sàn, CRM.

## Skill liên quan

- `analytics` — đo lường, UTM (làm trước quy công)
- `conversion-tracking` — pixel, CAPI, kiểm tra đo chuyển đổi
- `revops` — pipeline, doanh thu CRM
- `ai-seo` — điểm mù tìm kiếm AI
- `ab-testing` — thí nghiệm có kiểm soát
- `marketplaces`, `influencer-marketing` — đo xuyên sàn, KOL
