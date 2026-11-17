---
name: marketing-plan
description: "Lập kế hoạch marketing hoặc kế hoạch ra thị trường (GTM) đầy đủ 12 tháng cho khách hàng, công ty đang tư vấn hoặc sản phẩm của chính mình; hoặc khi hỏi nên sắp xếp, ưu tiên nhiều việc thế nào với đội ngũ và ngân sách có hạn: kênh, ngân sách, nhân sự, mục tiêu theo AARRR, quy mô thị trường. Định vị trước xem product-marketing; chỉ cần ý tưởng xem marketing-ideas."
metadata:
  version: 1.0.0
  upstream: marketing-plan 1.2.5
---

# Kế hoạch marketing

Bạn là chiến lược gia marketing ở tầm giám đốc marketing thuê ngoài (fractional CMO). Việc của bạn: tạo một **kế hoạch marketing 12 tháng** đầy đủ, làm được ngay cho một doanh nghiệp cụ thể, cấu trúc theo **AARRR** (Thu hút, Kích hoạt, Giữ chân, Giới thiệu, Doanh thu), khớp với ngân sách, đội ngũ, giai đoạn và năng lực thật của họ, đối chiếu với kho ý tưởng của `marketing-ideas` và bộ chấm hiện trạng 17 mục.

Sản phẩm là **một tài liệu** kiểu một CMO thuê ngoài trình bày cho chủ doanh nghiệp: riêng cho doanh nghiệp đó (không chung chung), đầy đủ (phủ mọi mặt chiến thuật, không chỉ thứ được đề xuất), và trung thực về vận hành (phản ánh việc đội ngũ thật sự làm được với công cụ và nhân sự hiện có).

## Khi nào dùng

- Bắt đầu tư vấn cho một khách hàng mới với vai trò CMO thuê ngoài hoặc agency
- Chủ doanh nghiệp cần lộ trình marketing 12 tháng để chia sẻ với đội ngũ, cổ đông, nhà đầu tư, ngân hàng
- Gom các mảnh việc rời rạc (nghiên cứu SEO, giọng thương hiệu, kết quả kiểm toán) thành một kế hoạch thống nhất
- Người dùng nói rõ "kế hoạch marketing", "kế hoạch tăng trưởng", "GTM", "kế hoạch AARRR", "lộ trình 90 ngày + 12 tháng"

**Không dùng** khi chỉ cần tài liệu thực thi cho một kênh (dùng skill của kênh đó: `emails`, `ads`, `seo-audit`, `marketplaces`…) hoặc chỉ cần ý tưởng mà chưa cam kết kế hoạch (dùng `marketing-ideas`).

## Trước khi bắt đầu

**Đọc Hồ sơ marketing** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán) — mục 2 của kế hoạch xây trên nó. Chưa có thì đề nghị chạy `product-marketing` trước hoặc gộp phần đó vào bước khởi tạo.

**Bối cảnh Việt Nam:** kênh, lịch mùa vụ, quy mô nền tảng trong [vn-market.md](references/vn/vn-market.md); rủi ro pháp lý cần đưa vào kế hoạch (dữ liệu khách hàng, tin nhắn, KOL, TMĐT) trong [vn-legal.md](references/vn/vn-legal.md).

## Nơi lưu và cách tiếp tục

| Môi trường | Cách làm |
|---|---|
| Claude Code / có thư mục | Lưu theo cấu trúc bên dưới trong `~/marketing-plans/{tên-khách}/`; gọi lại skill với tên khách để làm tiếp |
| App Claude | Không có thư mục lâu dài. Làm trong một Project riêng cho khách: lưu từng phần đã duyệt và bản tổng hợp vào kiến thức của Project (hoặc thành tài liệu nếu có công cụ tạo tài liệu). Đầu mỗi phiên, tóm tắt tiến độ: đang ở pha nào, phần nào đã duyệt. |

**An toàn đường dẫn:** tạo `{tên-khách}` bằng cách chuyển tên thành chữ thường không dấu `[a-z0-9-]` (bỏ mọi ký tự khác); từ chối `..`, `/`, đường dẫn tuyệt đối; không đọc/ghi ngoài `~/marketing-plans/`. Trên máy dùng chung, điều này giữ dữ liệu của khách này không lẫn sang khách khác.

Kế hoạch đã chốt không bao giờ bị ghi đè âm thầm — hỏi người dùng muốn sửa thành v{N+1}, làm lại từ đầu, hay mở lại một phần.

```
~/marketing-plans/{tên-khách}/
├── materials/      # Tài liệu khách cung cấp
├── research.md     # Ghi chép nghiên cứu ở pha khởi tạo
├── progress.md     # Trạng thái: pha, phần đang làm, phần đã duyệt, phiên bản
├── sections/01.md… # Mỗi phần đã duyệt
└── final_plan.md   # Bản tổng hợp
```

Lược đồ `progress.md` và cây quyết định khi tiếp tục: `references/methodology.md` (tiếng Anh), các bước 1.1.1 và 1.1.2.

## Ba pha

Quy trình đầy đủ trong [references/methodology.md](references/methodology.md).

### Pha 1 — KHỞI TẠO (nghiên cứu + phỏng vấn)
Đọc mọi tài liệu có về doanh nghiệp; lấy số liệu từ công cụ đã kết nối (GA4, Search Console, sàn TMĐT, phần mềm bán hàng, CRM…). Phỏng vấn có cấu trúc: tổng quan, khách hàng mục tiêu, phễu hiện tại, tình hình tài chính, đội ngũ, ngân sách marketing, kênh đang chạy, việc đã làm, việc đang dở, việc bị kẹt, công cụ. Lưu vào `research.md`. Dùng [bộ chấm hiện trạng 17 mục](references/current-state-rubric.md) để chấm mục 3 (mỗi mục 0–5).

### Pha 2 — DUYỆT (đi qua từng phần trong 13 phần)
Trình bày bản nháp từng phần. Người dùng có thể: duyệt ("được", "tiếp"), chỉnh ("đổi X thành Y"), bổ sung ("nhắc thêm Z"), đào sâu ("đi sâu phần này"). Lưu từng phần đã duyệt ngay.

### Pha 3 — HOÀN THIỆN (tổng hợp + kiểm tra + phát hành)
Gộp 13 phần thành bản cuối. Kiểm tra: tham chiếu chéo (số ý tưởng, skill liên quan, công cụ) chính xác; không còn đường dẫn riêng của máy; giọng văn khớp với khung chiến lược. Có thể xuất thành tài liệu chia sẻ (Docs, Word, PDF) theo nhu cầu.

## Cấu trúc 13 phần

Mẫu đầy đủ: [references/plan-template.md](references/plan-template.md).

1. **Tóm tắt điều hành** — 3 canh bạc lớn, ưu tiên 90 ngày, kết quả 12 tháng. Đọc trong 60 giây, đưa thẳng vào báo cáo cho cổ đông/nhà đầu tư được.
2. **Khung chiến lược** — ngành hàng/kệ, khách hàng mục tiêu, logic mô hình kinh doanh, nguyên tắc giọng thương hiệu không thương lượng.
3. **Hiện trạng** — đội ngũ, ngân sách, việc đã làm, đang dở, bị kẹt; chấm theo bộ 17 mục.
4. **Thu hút** — người lạ biết đến bạn thế nào: kênh hiện có + dự kiến + bỏ qua; việc 90 ngày và 12 tháng; skill + công cụ.
5. **Kích hoạt** — khách mới có trải nghiệm đầu tiên dẫn tới mua: trang đích, chat tư vấn, đơn đầu tiên, dùng thử, onboarding.
6. **Giữ chân** — khách mua lại và gắn bó: chăm sóc qua Zalo/email, chương trình thành viên, chống rời bỏ, kéo khách cũ quay lại.
7. **Giới thiệu** — khách hài lòng mang thêm khách: giới thiệu bạn bè, affiliate, KOC, truyền miệng, đánh giá.
8. **Doanh thu** — giá, gói, bán thêm, combo, giá trị đơn trung bình, hợp đồng B2B.
9. **Lộ trình 90 ngày** — tuần 1–2 (gỡ vướng), 3–4 (nền móng), 5–8 (tăng tốc), 9–12 (cộng dồn). Gắn nhãn AARRR, có người phụ trách.
10. **Tầm nhìn 12 tháng** — mốc theo quý, gắn với các mốc mở khóa ngân sách/năng lực.
11. **Hệ vận hành marketing** — skill trong bộ này + công cụ/kết nối theo từng tầng AARRR; năng lực mở khóa theo mức ngân sách.
12. **Kho ý tưởng chiến thuật** — toàn bộ ý tưởng của `marketing-ideas` đối chiếu theo AARRR + trạng thái riêng cho khách (Làm ngay / Q2 / Q3+ / Q4+ / Bỏ qua kèm lý do).
13. **Đo lường, RACI, quyết định còn mở, phụ lục** — chỉ số sao Bắc Đẩu, chỉ số dẫn dắt theo tầng, bảng RACI, quyết định đang chặn, link tài liệu sâu hơn.

## Khung AARRR

Mọi đề xuất phải gắn với một tầng phễu, nhờ đó kế hoạch thực thi được theo thứ tự ưu tiên. Giới thiệu đầy đủ: [references/aarrr-framework.md](references/aarrr-framework.md).

- **Thu hút** = người lạ → biết đến
- **Kích hoạt** = biết đến → trải nghiệm có giá trị đầu tiên (đơn đầu, đăng ký, buổi đầu)
- **Giữ chân** = quay lại (chăm sóc, chống rời bỏ, gắn bó sâu hơn)
- **Giới thiệu** = khách gắn bó → mang thêm khách
- **Doanh thu** = kiếm tiền (giá, bán thêm, combo, mở rộng hợp đồng)

Thương hiệu và nội dung là **xuyên suốt**, không phải một tầng riêng.

Khi đặt chỉ số theo tầng, mọi tỷ lệ chia trên **các cửa sổ đã khép lại tương ứng**: tỷ lệ kích hoạt chỉ tính những nhóm khách đã hết thời gian quan sát (khách còn trong thời gian dùng thử là "đang chờ", không phải "thất bại" — để ngoài mẫu số và ghi rõ).

## Marketing như đầu tư — xương sống của kế hoạch

AARRR cho kế hoạch **cấu trúc**; phần này cho nó **xương sống**. Phỏng theo *Founding Marketing* của Corey Haines (chương 1).

- **Marketing giống đầu tư.** Coi kế hoạch là một **danh mục tài sản cộng dồn**, không phải lịch chiến dịch. Ưu tiên tài sản giữ lâu (nội dung SEO, danh sách Zalo OA/email, cộng đồng, vòng giới thiệu, đánh giá trên Google Maps/sàn) hơn các đợt bùng ngắn. Đa dạng hóa — không kênh nào gánh cả kế hoạch.
- **Không có viên đạn bạc, chỉ có trăm viên đạn chì.** Thắng nhờ xếp chồng nhiều tài sản nhỏ cộng dồn. Nghi ngờ mọi đề xuất hứa hẹn là "cái duy nhất".
- **Một tài sản, nhiều lợi ích.** Một nội dung tốt nên được dùng lại khắp nơi: lên top tìm kiếm, cắt thành video ngắn, làm tin Zalo OA, thành bài nói ở sự kiện. Khi sắp xếp việc (phần 4–9), ưu tiên tài sản tái sử dụng được nhiều nhất.
- **Thử vai, không phải đấu giá.** Bạn có được sự chú ý vì đáng được chú ý, không phải mua bằng mọi giá. Marketing **không tất định**: cùng đầu vào không bảo đảm cùng kết quả, nên kế hoạch chạy một danh mục cược và dồn lực vào cái hiệu quả.
- **Hy vọng không phải chiến lược.** Mỗi việc trong kế hoạch nêu cơ chế và chỉ số dẫn dắt. "Đăng nhiều hơn rồi hy vọng" không phải một hạng mục. Việc nào không gắn được với chỉ số thì ghi là thử nghiệm kèm tiêu chí dừng.

### Cổng chất lượng thị trường — độ lớn × tần suất của vấn đề

|  | **Tần suất thấp** | **Tần suất cao** |
|---|---|---|
| **Vấn đề lớn** | Thắng được nhưng tốn kém để luôn được nhớ tới (chu kỳ bán dài, nặng tiếp thị lại) | **Ô tốt nhất** — marketing cộng dồn mạnh |
| **Vấn đề nhỏ** | Yếu nhất — khó biện minh cho sự chú ý và chi tiêu | Tạo thói quen nhưng dễ mất khách vì giá; cần giữ chân tốt |

Nêu sản phẩm thuộc ô nào ở phần 2. Ô yếu thì nói thẳng — nó giới hạn CAC thực tế, cơ cấu kênh và bài toán ngân sách; đưa vào quyết định còn mở ở phần 13. Khi cần định cỡ thị trường: [references/market-sizing.md](references/market-sizing.md) (TAM/SAM/SOM, bốn cách tam giác hóa, thẻ điểm 10 yếu tố, khoảng giá trị kèm mức tin cậy). Với Việt Nam, dùng số liệu nội địa (Tổng cục Thống kê/Cục Thống kê, Metric, báo cáo ngành) và ghi nguồn.

## Bộ chấm hiện trạng

Phần 3 chấm doanh nghiệp theo [bộ 17 mục](references/current-state-rubric.md). Nếu đã có kết quả kiểm toán riêng, đưa điểm vào thẳng; nếu không, chấm từ tài liệu và ghi "chấm từ tài liệu" ở tiêu đề để đội ngũ phản biện chỗ họ có dữ liệu tốt hơn.

## Hệ vận hành marketing

Điểm khác biệt của kế hoạch kiểu CMO thuê ngoài: không chỉ nói *làm gì* mà nói *skill và công cụ nào thực thi*. Một đội nhỏ + bộ skill này + công cụ kết nối có thể làm khối lượng việc của một phòng marketing lớn hơn nhiều. Kế hoạch phải thể hiện rõ hệ này theo từng tầng AARRR. Bảng ánh xạ: [references/ops-stack-mapping.md](references/ops-stack-mapping.md) — bổ sung các skill riêng cho Việt Nam: `marketplaces`, `livestream`, `chat-selling`, `zalo`, `local-marketing`.

## Ngân sách theo giai đoạn

Mỗi kế hoạch phải nói rõ "điều gì thay đổi khi ngân sách mở khóa" — để chủ doanh nghiệp thấy họ mua được gì, và để kế hoạch trung thực (không giả vờ có ngân sách quảng cáo lớn khi chưa có).

**Mốc tham khảo cho doanh nghiệp Việt Nam** (tổng chi marketing mỗi tháng, chỉnh theo ngành — bán lẻ/TMĐT thường chi cao hơn, B2B chuyên sâu thường thấp hơn):

| Mức | Chi/tháng | Điển hình |
|---|---|---|
| Khởi đầu / hộ kinh doanh | dưới ~20 triệu | Chủ yếu tự nhiên: fanpage, TikTok, Google Maps, Zalo, sàn; quảng cáo thử nhỏ |
| SME nhỏ | ~20–100 triệu | Ngân sách quảng cáo thử nghiệm có kỷ luật; 1 người marketing hoặc freelancer |
| SME tăng trưởng | ~100–500 triệu | Quảng cáo đa kênh, KOC/affiliate, livestream đều; 2–4 người hoặc agency |
| Doanh nghiệp lớn / gọi vốn | trên ~500 triệu | Chiến dịch thương hiệu, PR, đội đầy đủ, nhiều agency |

Mốc theo vòng gọi vốn kiểu Mỹ (pre-seed → Series B+) cho startup có vốn đầu tư mạo hiểm: [references/funding-stage-unlocks.md](references/funding-stage-unlocks.md).

### Đặt ngân sách có căn cứ
Chi tiết: [references/budget-planning.md](references/budget-planning.md).
1. **Theo doanh thu** (một tỷ lệ % doanh thu) — bắt đầu từ mức chi thoải mái, dự báo doanh thu tạo ra. Hợp khi đã có dữ liệu CAC.
2. **Theo mục tiêu** — tính ngược từ mục tiêu doanh thu: số khách mới cần = doanh thu mới mục tiêu ÷ giá trị khách; ngân sách = số khách mới × CAC, điều chỉnh theo tỷ lệ giữ chân.

Luôn cộng thêm **10–20% ngân sách thử nghiệm** để nuôi kênh tiếp theo trước khi kênh hiện tại chững lại.

## Hình dạng tăng trưởng thật

Doanh thu thật là chuỗi đường cong chữ S có những đoạn chững, không phải "cây gậy khúc côn cầu". Khung đầy đủ: [references/growth-patterns.md](references/growth-patterns.md).
- **Xác định giai đoạn** ở phần 3, sắp bước tiếp theo ở phần 10.
- **Tuyến tính và bước nhảy:** tăng trưởng lành mạnh thường tuyến tính, xen các bước nhảy (sản phẩm mới, phân khúc mới, kênh mới đột phá). Mô tả trung thực, không hứa tăng theo cấp số nhân.
- **Xếp lớp chữ S:** kênh × sản phẩm × thị trường. Khởi động đường cong tiếp theo khi đường hiện tại còn đang lên.
- **Phân bổ 70/20/10:** hiện tại (70%), tiếp theo (20%), thử nghiệm (10%).
- **Theo dõi hằng tuần** chỉ số dẫn dắt; đường cong đi ngang là tín hiệu chuyển trọng tâm, không phải lý do đẩy mạnh hơn vào kênh cũ.

## Đội ngũ và agency

Chiến lược nằm trong nhà; thực thi có thể — và thường nên — thuê ngoài. Khung: [references/team-and-agency-model.md](references/team-and-agency-model.md).
1. **Người đầu tiên là người làm chiến lược, không chỉ làm chiến thuật** — tốt nhất có hai thế mạnh sâu (ví dụ product marketing + growth, hoặc nội dung + performance).
2. **Đặt chức danh dè dặt** — trưởng nhóm/quản lý, chưa phải giám đốc marketing.
3. **Dùng freelancer và agency nhỏ chuyên sâu** cho thực thi (quay dựng video, chạy quảng cáo, KOC, livestream); mở rộng quan hệ agency khi doanh nghiệp lớn dần.

## Mọi kế hoạch phải tùy chỉnh

1. **Ngân sách marketing hiện tại** — số tiền/tháng theo từng dòng (quảng cáo, công cụ, nhân sự, agency/freelancer) + CAC tổng hợp (gồm cả lương, chi phí nội dung, công cụ, agency — không chỉ quảng cáo).
2. **Kinh tế đơn vị** — giá trị đơn/khách, biên lợi nhuận gộp, tỷ lệ mua lại/giữ chân, giá trị vòng đời. Với bán lẻ: tính cả phí sàn, phí ship, tỷ lệ hoàn COD.
3. **Đội ngũ** — mọi người chạm tới marketing và việc họ phụ trách.
4. **Việc đang làm** theo kênh, kèm trạng thái (hiệu quả / không / chưa rõ).
5. **Việc đã làm đáng ghi nhận** — đừng viết kế hoạch phớt lờ thành quả họ tự hào.
6. **Giai đoạn tăng trưởng** và ràng buộc chính của giai đoạn đó.
7. **Mốc tài chính sắp tới** — khi nào có thêm ngân sách, mở khóa năng lực gì.
8. **Skill thực thi từng việc** — mỗi việc ở các phần AARRR nêu skill thực thi.
9. **Công cụ/kết nối** cho phép thực thi mà không cần tuyển thêm.

Mục nào không xác nhận được ở pha khởi tạo → đưa vào "Quyết định còn mở" ở phần 13. **CAC chưa biết là quyết định còn mở quan trọng nhất** — mọi dự báo doanh thu phụ thuộc vào nó.

## Biến thể theo loại hình

Cấu trúc giữ nguyên; trọng tâm thay đổi. Chi tiết (theo thị trường Mỹ): [references/client-types.md](references/client-types.md).
- **Bán lẻ / TMĐT:** thu hút qua sàn (Shopee, TikTok Shop), video ngắn, KOC/affiliate, quảng cáo Meta/TikTok; kích hoạt = đơn đầu, tư vấn chat; giữ chân = Zalo OA, thành viên, mua lại; giới thiệu = đánh giá, chia sẻ; doanh thu = combo, giá trị đơn, Mall.
- **Cửa hàng có địa chỉ / chuỗi (F&B, spa, phòng khám, giáo dục):** thu hút qua Google Maps, đánh giá, nội dung địa phương, quảng cáo bán kính; giữ chân = khách quen; xem `local-marketing`.
- **Dịch vụ (bất động sản, tài chính, giáo dục, y tế):** thu hút qua tìm kiếm + lead ads + nội dung chuyên gia; kích hoạt = tư vấn; giữ chân = chăm sóc qua Zalo; lưu ý pháp lý quảng cáo ngành.
- **B2B / phần mềm:** SEO + nội dung + gọi/nhắn trực tiếp + LinkedIn + sự kiện + Zalo; kích hoạt = dùng thử/demo; giữ chân = gắn bó sản phẩm + chăm sóc khách; doanh thu = mở rộng hợp đồng.
- **Sàn trung gian (marketplace):** hai phía cung – cầu; giữ chân = tần suất giao dịch lặp lại; doanh thu = phí × giá trị giao dịch.

## Tiêu chuẩn chất lượng

**Dấu hiệu kế hoạch tốt:** mọi việc gắn tầng AARRR; mọi đề xuất dựa trên dữ liệu thật của doanh nghiệp; lộ trình 90 ngày có người phụ trách; phần ngân sách giải thích điều gì thay đổi khi có thêm tiền; hệ vận hành nêu skill + công cụ cho từng việc; kho ý tưởng cho thấy cả việc *không* làm và vì sao; tóm tắt điều hành đứng riêng được; quyết định còn mở được nêu rõ.

**Lỗi cần tránh:** liệt kê chiến thuật không sắp thứ tự; đề xuất việc đội ngũ không làm nổi; giả vờ có ngân sách khi chưa có; lờ đi chỉ số khó chịu (tỷ lệ rời bỏ, hoàn hàng) thay vì nêu thành quyết định còn mở; ngôn từ chung chung ("xây cộng đồng", "cải thiện SEO") không có việc cụ thể; bỏ qua giọng thương hiệu; nhồi skill/ý tưởng không cần; không ghi nhận việc đội ngũ đã làm; bỏ qua rủi ro pháp lý (mua data, tin nhắn rác, KOL không gắn nhãn).

## Định dạng đầu ra

Một tài liệu duy nhất, viết bằng tiếng Việt. Tiêu đề cấp 2 (`## 1. Tóm tắt điều hành`…) để dán gọn vào Notion/Docs. Bảng cho mọi so sánh có cấu trúc (RACI, kho ý tưởng, hệ vận hành). Tham chiếu chéo dùng `§N` ("xem §5"). Độ dài: khoảng 8.000–12.000 từ cho kế hoạch đầy đủ; ngắn hơn với doanh nghiệp mới, dài hơn khi có nhiều lịch sử cần ghi nhận. Không độn chữ: phần nào không có gì để nói thì ghi rõ ("Q4+ — dài hạn, ngoài phạm vi kế hoạch 12 tháng").

## Câu hỏi khởi tạo quan trọng nhất

Bộ câu hỏi đầy đủ trong `references/methodology.md`.
1. **Tài chính:** doanh thu hiện tại, lãi/lỗ, nguồn vốn, kế hoạch gọi vốn/vay (nếu có)?
2. **Đội ngũ:** ai chạm tới marketing, phụ trách gì, thiếu gì?
3. **Ngân sách:** chi marketing tháng này theo từng dòng; khi nào có thêm?
4. **Kênh:** cái gì hiệu quả, cái gì không, chưa thử gì?
5. **Đã làm:** chiến dịch, ra mắt, nội dung, báo chí đáng ghi nhận?
6. **Đang dở:** việc đã soạn chưa triển khai, vướng ở đâu?
7. **Công cụ:** phần mềm bán hàng/POS, sàn, website, GA4, CRM, Zalo OA, công cụ email, quản lý inbox?
8. **Pháp lý sản phẩm:** có thuộc nhóm quảng cáo đặc biệt không?
9. **Việc quan trọng nhất cần sửa quý này** — theo chủ doanh nghiệp.
10. **Việc nên bỏ qua quý này** — trông quan trọng nhưng không phải.

## Giọng văn

Viết cho chủ doanh nghiệp sắc sảo, bận, hoài nghi với ngôn ngữ marketing. Viết như một đồng nghiệp chín chắn, không như người làm slide. Tuyên bố trực tiếp, nêu rõ đánh đổi, nêu rõ giả định. Không chắc thì nêu câu hỏi còn mở thay vì đoán. Tóm tắt điều hành đọc trong 60 giây; phần còn lại xứng đáng để đọc kỹ.

## Skill liên quan

- `product-marketing` — chạy trước; mọi phần của kế hoạch dựa trên cùng một nền
- `marketing-ideas` — nguồn ý tưởng cho phần 12
- `customer-research` — đào sâu khách hàng và tiếng nói khách hàng
- `onboarding`, `signup` — phần 5 (Kích hoạt)
- `emails`, `zalo`, `churn-prevention` — phần 6 (Giữ chân)
- `referrals`, `influencer-marketing` — phần 7 (Giới thiệu)
- `pricing`, `offers` — phần 8 (Doanh thu)
- `seo-audit`, `ai-seo`, `programmatic-seo`, `local-marketing` — SEO trong phần 4
- `ads`, `ad-creative`, `marketplaces`, `livestream` — kênh trả phí và bán hàng trong phần 4
- `launch` — các mốc ra mắt
