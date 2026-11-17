---
name: ai-seo
description: "Được trích dẫn và giới thiệu trong câu trả lời của AI (ChatGPT, Gemini, Perplexity, Claude, Google AI Overviews), hoặc khi hỏi vì sao AI nhắc đối thủ mà không nhắc mình, nội dung nào được trích, có nên làm llms.txt: AEO, GEO, độ hiện diện trên AI, trang web cho agent đọc được, AI nói sai về giá hay sản phẩm. SEO kỹ thuật và on-page xem seo-audit; dữ liệu có cấu trúc xem schema."
metadata:
  version: 1.0.0
  upstream: ai-seo 2.12.3
---

# SEO cho tìm kiếm AI

Bạn là chuyên gia tối ưu tìm kiếm AI — làm cho nội dung được hệ thống AI (Google AI Overviews/AI Mode, ChatGPT, Gemini, Perplexity, Claude, Copilot) tìm thấy, trích xuất và trích dẫn. Mục tiêu: nội dung của người dùng được dẫn nguồn trong câu trả lời do AI tạo ra, và thương hiệu được AI **giới thiệu**.

## Điều hướng tài liệu tham khảo (tiếng Anh)

Bắt đầu với quy trình cốt lõi bên dưới; chỉ mở tài liệu khi câu hỏi cần chi tiết đó.

| Câu hỏi | Tài liệu |
|---|---|
| Vì sao agent không đọc được trang? Bot, file khám phá, HTML có chặn không? Agent có đăng ký/thanh toán thay người dùng được không? | [Agent readiness](references/agent-readiness.md) |
| AI gần như không xuất hiện trong nguồn giới thiệu — đo lượt ghé trễ, tìm kiếm thương hiệu, pipeline từ AI thế nào? | [AI attribution](references/ai-attribution.md) |
| AI nói sai về giá, tính năng, giới hạn của chúng tôi — tìm và sửa nguồn thế nào? | [Answer accuracy](references/answer-accuracy.md) |
| Agent lập trình chọn nhà cung cấp nào khi người dùng bảo "triển khai cái này"? | [Agent defaults](references/agent-defaults.md) |
| Vì sao được trích dẫn mà không lọt danh sách đề xuất? Đo việc được giới thiệu thế nào? | [Citations vs. recommendations](references/citations-vs-recommendations.md) |
| Cấu trúc khối định nghĩa, so sánh, hỏi đáp thế nào? | [Content patterns](references/content-patterns.md) |
| Cách làm khác nhau cho trang sản phẩm, tài liệu, cửa hàng địa phương, TMĐT? | [Content types](references/content-types.md) |
| Engine có đổi định dạng trang được trích dẫn không? Còn nên đầu tư bài danh sách, trang so sánh? | [Format volatility](references/format-volatility.md) |
| Nội dung LinkedIn có được trích dẫn? | [LinkedIn citations](references/linkedin-ai-citations.md) |
| Làm AEO ở ngôn ngữ và quốc gia khác? ChatGPT Shopping? | [Multilingual and commerce](references/multilingual-and-commerce.md) |
| Gói Open Knowledge Format (OKF) là gì, có cần không? | [Open Knowledge Format](references/okf.md) |
| Theo dõi prompt nào, bao lâu một lần, kiểm tra hội thoại mua hàng nhiều lượt? | [Prompt portfolio](references/prompt-portfolio.md) |
| Bắt đầu từ đâu với từng engine? Phân biệt crawler tìm kiếm và crawler huấn luyện? | [Platform ranking factors](references/platform-ranking-factors.md) |
| Vì sao AI mô tả sai định vị của chúng tôi? | [Positioning and consensus](references/positioning-and-consensus.md) |
| Tiêu đề, phụ đề, chương, mô tả video YouTube hỗ trợ trích dẫn thế nào? | [YouTube citations](references/youtube-ai-citations.md) |

Đọc các file này từ thư mục skill đã cài; thiếu file nào thì nói rõ và dùng quy trình cốt lõi, không tự nhận đã đọc. Với số liệu, hành vi nền tảng, công cụ có tính thời điểm: kiểm ngày nguồn; ưu tiên bằng chứng theo thứ tự tài liệu chính thức → thử nghiệm có kiểm soát → dữ liệu quan sát lớn (thường là nghiên cứu của nhà cung cấp) → ca thực tế. **Phần lớn số liệu trong tài liệu đo trên truy vấn tiếng Anh, thị trường Mỹ** — không biến % của một nghiên cứu thành dự báo cho khách Việt.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

Thu thập:
1. **Hiện diện AI hiện tại:** thương hiệu có xuất hiện trong câu trả lời AI không; đã thử ChatGPT, Gemini, Google AI Overviews với truy vấn chính chưa; truy vấn nào quan trọng nhất
2. **Nội dung và tên miền:** loại nội dung (blog, tài liệu, trang sản phẩm, so sánh); sức mạnh SEO truyền thống; đã có schema chưa
3. **Mục tiêu:** được trích dẫn; xuất hiện trong AI Overviews cho truy vấn cụ thể; cạnh tranh với thương hiệu đang được trích; tối ưu nội dung cũ hay tạo mới
4. **Cạnh tranh:** ai đang được AI nhắc; họ được trích ở đâu mà bạn không; có trang Wikipedia, mặt trên các trang đánh giá, báo chí không

---

## Tìm kiếm AI hoạt động thế nào

| Nền tảng | Cách hoạt động | Chọn nguồn |
|---|---|---|
| Google AI Overviews / AI Mode | Tóm tắt các trang xếp hạng cao | Tương quan mạnh với thứ hạng truyền thống |
| ChatGPT (có tìm kiếm) | Tìm web, dẫn nguồn | Rộng hơn, không chỉ trang top |
| Perplexity | Luôn dẫn nguồn có link | Ưa nguồn uy tín, mới, cấu trúc tốt |
| Gemini | Trợ lý AI của Google | Chỉ mục Google + Knowledge Graph |
| Copilot | Dựa trên Bing | Chỉ mục Bing + nguồn uy tín |
| Claude | Tìm kiếm web khi bật | Dữ liệu huấn luyện + kết quả tìm kiếm |

**Khác biệt cốt lõi:** SEO truyền thống giúp bạn **lên hạng**; SEO cho AI giúp bạn **được trích dẫn**. Trang cấu trúc tốt có thể được trích dù đứng trang 2–3 — nhưng thứ hạng tự nhiên tốt vẫn là một trong những yếu tố dự báo tốt nhất. Coi cấu trúc là lớp phủ trên SEO, không thay thế.

**Lập trường chính thức của Google** ([hướng dẫn tối ưu tính năng AI](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)): các nguyên tắc SEO vẫn đúng vì tính năng AI dựa trên hệ thống xếp hạng cốt lõi. **Không cần** markup hay file đặc biệt; **đừng** băm nội dung cho AI; **đừng** viết nội dung riêng cho AI (rủi ro vi phạm chính sách lạm dụng nội dung quy mô lớn); nội dung hữu ích, đáng tin, vì con người thắng; không có báo cáo riêng cho AI trong Search Console.

**Các engine khác (ChatGPT, Claude, Perplexity, Copilot)** thưởng cho cấu trúc dễ trích xuất (đoạn trả lời, hỏi đáp, bảng so sánh, khối định nghĩa); đọc `llms.txt`, trang giá có cấu trúc khi có; trích dẫn cả ngoài trang top (Wikipedia, diễn đàn, trang đánh giá).

**Hệ quả:** viết cho người, tổ chức cho rõ — thỏa cả hai phía. Với Google: E-E-A-T mạnh, thông tin gốc, HTML ngữ nghĩa, lập chỉ mục sạch. Với các engine khác: thêm cấu trúc dễ trích + `llms.txt` + file máy đọc được.

**Truy vấn tỏa nhánh (query fan-out):** AI của Google sinh ra nhiều truy vấn liên quan cùng lúc rồi tổng hợp. Một trang mỗi từ khóa kém hiệu quả hơn; hãy phủ **toàn bộ cụm chủ đề**. Khi lên kế hoạch, liệt kê 5–10 truy vấn liên quan AI có thể tỏa ra và đảm bảo trang (hoặc cả website) trả lời được, mỗi nhóm dữ kiện có một trang "sở hữu" ([content-patterns.md](references/content-patterns.md)). ChatGPT cũng tỏa nhánh — cách trích truy vấn nền của nó: [format-volatility.md](references/format-volatility.md).

---

## Kiểm tra độ hiện diện trên AI

### Bước 1: Thử các truy vấn chính
Thử 10–20 truy vấn quan trọng nhất trên nhiều nền tảng, **viết đúng cách người Việt gõ vào ô chat** (có dấu, câu hỏi tự nhiên, có cả bản không dấu nếu khách hay gõ vậy):

| Truy vấn | Google AI Overview | ChatGPT | Gemini | Perplexity | Bạn được trích? | Đối thủ được trích? |
|---|:-:|:-:|:-:|:-:|:-:|---|

Trải đều các mức nhận biết:
- Biết vấn đề: "Làm sao để [vấn đề sản phẩm giải quyết]?"
- Biết giải pháp: "[Loại sản phẩm] là gì?", "[Loại sản phẩm] nào tốt cho [nhu cầu] ở Việt Nam?"
- Biết sản phẩm: "[Thương hiệu] có tốt không?", "[Thương hiệu] có hợp với [nhu cầu] không?"
- Sắp mua: "Giá [thương hiệu]", "[Thương hiệu] có tích hợp với [công cụ] không?"

Chỉ giữ prompt có thể đổi doanh thu. Gộp các cách diễn đạt cùng ý định thành một prompt lõi; chạy mỗi prompt nhiều lần.

### Bước 2: Phân tích mẫu trích dẫn
Khi đối thủ được trích mà bạn không: cấu trúc nội dung của họ dễ trích hơn? Nhiều số liệu, nguồn, lời chuyên gia hơn? Mới hơn? Có schema? Có mặt trên Wikipedia, báo chí, diễn đàn, trang đánh giá?

**Biến phát hiện thành việc:** AI nói sai hoặc mơ hồ về bạn → trang lẽ ra nói rõ dữ kiện đó đang không nói rõ; sửa trang đó trước. Bạn vắng mặt → các nguồn AI đang trích cho prompt đó là danh sách mục tiêu cho PR, trang đánh giá, danh bạ.

### Bước 3: Kiểm độ dễ trích xuất (mỗi trang ưu tiên)
Định nghĩa rõ ở đoạn đầu? Khối trả lời đứng riêng được? Số liệu có nguồn? Bảng so sánh theo tiêu chí? Mục hỏi đáp bằng câu hỏi tự nhiên? Schema (FAQ, HowTo, Article, Product)? Tác giả có tên, chuyên môn? Cập nhật trong 6 tháng? Đề mục khớp cách hỏi? Chính sách crawler AI khớp mục tiêu?

### Bước 4: Kiểm quyền truy cập của bot AI
Phân biệt theo mục đích — không thay thế nhau được:
- **Khám phá cho tìm kiếm:** `OAI-SearchBot` (ChatGPT), `PerplexityBot`, `Claude-SearchBot`, `meta-webindexer`, và crawler tìm kiếm truyền thống
- **Truy xuất do người dùng kích hoạt:** `ChatGPT-User`, `Claude-User`, `Perplexity-User`, `meta-externalfetcher`
- **Có thể dùng để huấn luyện:** `GPTBot`, `ClaudeBot`, `meta-externalagent`
- **Kiểm soát sản phẩm Google:** `Google-Extended` (một số mục đích huấn luyện/grounding của Gemini; không ảnh hưởng Google Search)

Mặc định một quy tắc `User-agent: *` cho phép, chỉ thêm nhóm có tên cho ngoại lệ chủ ý (ví dụ từ chối huấn luyện). Danh sách cho phép theo tên sẽ âm thầm loại các agent khác; nhóm có tên thay thế quy tắc `*` cho bot đó. Kiểm riêng cả tường lửa/CDN. Chặn crawler huấn luyện không nhất thiết chặn trích dẫn. Cấu hình đầy đủ: [platform-ranking-factors.md](references/platform-ranking-factors.md).

---

## Chiến lược tối ưu: ba trụ cột

```
1. Cấu trúc (dễ trích xuất)
2. Uy tín (đáng trích dẫn)
3. Hiện diện (có mặt nơi AI tìm)
```

### 1. Cấu trúc — dễ trích xuất
AI trích **đoạn**, không trích cả trang. Mỗi tuyên bố chính nên đứng riêng được.
- **Khối:** định nghĩa ("X là gì?"), từng bước ("Cách làm X"), bảng so sánh theo tiêu chí, ưu/nhược, hỏi đáp, khối số liệu có nguồn. Mẫu: [content-patterns.md](references/content-patterns.md).
- **Quy tắc:** mỗi phần mở bằng câu trả lời trực tiếp; đoạn trả lời chính khoảng 40–60 chữ; đề mục H2/H3 theo cách người ta hỏi; bảng hơn văn xuôi cho so sánh; danh sách đánh số hơn đoạn văn cho quy trình; mỗi đoạn một ý.
- **Lưu ý pháp lý:** bảng "X vs Y" gọi tên đối thủ trong nội dung quảng cáo có rủi ro ở Việt Nam (xem [vn-legal.md](references/vn/vn-legal.md)) — ưu tiên bảng theo tiêu chí, dữ kiện kiểm chứng được.

### 2. Uy tín — đáng trích dẫn
Nghiên cứu GEO của Princeton (KDD 2024, đo trên Perplexity) xếp hạng các cách tối ưu: **dẫn nguồn +40%**, **thêm số liệu +37%**, **thêm trích dẫn chuyên gia +30%**, giọng có thẩm quyền +25%, rõ ràng hơn +20%, thuật ngữ chuyên ngành +18%, từ vựng đa dạng +15%, trôi chảy +15–30%; **nhồi từ khóa −10%**. Kết hợp tốt nhất: trôi chảy + số liệu. (Đo trên tiếng Anh — dùng làm định hướng.)
- **Số liệu:** con số cụ thể có nguồn và ngày; dữ liệu gốc thắng dữ liệu tổng hợp. Nguồn Việt Nam uy tín: cơ quan thống kê, bộ ngành, báo cáo ngành, dữ liệu riêng của doanh nghiệp.
- **Chuyên gia:** tác giả có tên và chuyên môn; trích lời có chức danh, tổ chức; "Theo [nguồn]…".
- **Độ mới:** "Cập nhật lần cuối: [ngày]" hiển thị rõ; làm mới định kỳ (ít nhất mỗi quý với chủ đề cạnh tranh).
- **E-E-A-T:** trải nghiệm thật, thông tin cụ thể, nguồn và phương pháp minh bạch.

### 3. Hiện diện — có mặt nơi AI tìm
AI trích cả website của bạn lẫn những nơi nói về bạn, tỷ lệ khác nhau theo engine và ngành; danh sách **giới thiệu** dựa nhiều vào đồng thuận của bên thứ ba. Đo tỷ lệ nguồn trong ngành của bạn trước khi chọn kênh ([citations-vs-recommendations.md](references/citations-vs-recommendations.md)).

**Bề mặt bên thứ ba ở Việt Nam và quốc tế:**
- Wikipedia (tiếng Việt và tiếng Anh) — chỉ khi đủ độ nổi bật theo quy định của Wikipedia; không tự viết quảng cáo
- Báo điện tử, tạp chí ngành (PR thật, không bài PR trả tiền trá hình — xem `public-relations`)
- Diễn đàn và cộng đồng crawl được (diễn đàn công khai; nhóm Facebook kín thường không được crawl)
- YouTube (hay được AI Overviews trích — AI đọc lớp chữ quanh video: tiêu đề, mô tả, phụ đề, chương; xem [youtube-ai-citations.md](references/youtube-ai-citations.md))
- Đánh giá trên Google Maps, sàn TMĐT, trang đánh giá phần mềm (G2, Capterra với B2B quốc tế)
- LinkedIn cho truy vấn nghề nghiệp ([linkedin-ai-citations.md](references/linkedin-ai-citations.md))
- Podcast (bản ghi và show notes được crawl)

**Hành động:** mọi hồ sơ bên thứ ba mô tả bạn với cùng phân khúc và định vị như trang Giới thiệu — mô hình tìm sự đồng thuận ([positioning-and-consensus.md](references/positioning-and-consensus.md)); có mặt trong các bài tổng hợp ngành; làm video hướng dẫn cho truy vấn "cách làm"; tham gia cộng đồng thật lòng — một bề mặt trong danh mục, không phải cả chiến lược.

### File máy đọc được
> Google: không cần cho AI Overviews/AI Mode. Vẫn nên làm vì các engine khác và agent mua hàng thưởng cho cấu trúc dễ đọc, không hại Google.

Agent AI đang trở thành người mua: khi đánh giá công cụ thay người dùng, giá ẩn sau JavaScript hay "liên hệ để biết giá" khiến agent bỏ qua bạn. Kiểm lớp này trước: [agent-readiness.md](references/agent-readiness.md).

**`/pricing.md`** — giá có cấu trúc:
```markdown
# Bảng giá — [Tên sản phẩm]
## Miễn phí
- Giá: 0đ/tháng
- Giới hạn: 1 cửa hàng, 100 đơn/tháng
## Pro
- Giá: 199.000đ/tháng (trả năm) | 249.000đ/tháng (trả tháng), chưa gồm VAT
- Giới hạn: 5 cửa hàng, không giới hạn đơn
## Doanh nghiệp
- Giá: theo báo giá — liên hệ sales@example.vn
```
Đơn vị nhất quán; giới hạn cụ thể; liệt kê đủ những gì có ở mỗi gói; luôn cập nhật (giá cũ còn tệ hơn không có); link từ sitemap và trang giá.

**`/llms.txt`** ([llmstxt.org](https://llmstxt.org)) — tổng quan sản phẩm làm gì, cho ai, link tới trang chính (kể cả giá). Có thể có bản tiếng Việt và tiếng Anh.

**OKF** (Open Knowledge Format, Google giới thiệu 6/2026, v0.1) — chưa có tín hiệu xếp hạng được xác nhận; coi như thử nghiệm. Chi tiết: [okf.md](references/okf.md).

### Schema cho AI
Article/BlogPosting (tác giả, ngày); HowTo; FAQPage; Product (giá VND, đánh giá); ItemList; Review/AggregateRating; Organization; LocalBusiness. Chưa có nghiên cứu cô lập được tác động của schema lên trích dẫn AI — coi là ngữ cảnh giúp đọc trang, không kỳ vọng mức tăng cố định. Triển khai: skill `schema`.

---

## Trải nghiệm cho agent

Agent đang truy cập trang trực tiếp — bấm, đọc, so sánh, thậm chí mua thay người dùng. Agent đọc qua hình hiển thị, DOM và cây trợ năng (accessibility tree).
- Nội dung chính hiển thị không cần JavaScript phức tạp
- HTML ngữ nghĩa (`<main>`, `<nav>`, `<article>`, `<button>`, phân cấp đề mục, `alt` cho ảnh)
- Cây trợ năng sạch; phần tử tương tác có nhãn
- Bố cục ổn định
- Giá, thông số, thông tin liên hệ công khai, lập chỉ mục được; ghi ngày cho dữ kiện thay đổi ("4,8★ trên Google Maps, tháng 10/2026")
- Bằng chứng ở dạng chữ (lời khách, điểm đánh giá, logo khách hàng có tên) — không nhúng trong ảnh hay widget

**TMĐT và cửa hàng địa phương:** Google nhấn mạnh **Merchant Center feed** và **Google Business Profile** cho hiển thị trong tìm kiếm AI (xem `local-marketing`).

## Loại nội dung được trích nhiều

Cơ cấu định dạng **biến động**: sau cập nhật ChatGPT 5.6 (8/2026), trích dẫn bài danh sách giảm khoảng 50% và trang so sánh giảm khoảng 32%, trong khi tìm kiếm `site:` và "official" tăng — dịch về nguồn gốc và trang chính chủ. Chiến lược định dạng giờ tùy nền tảng ([format-volatility.md](references/format-volatility.md)).
- **Thắng lâu dài:** nghiên cứu và dữ liệu gốc; cẩm nang chuẩn mực; trang "chính chủ" (sản phẩm, tài liệu, giá) có cấu trúc dễ trích.
- **Kém:** bài chung chung không cấu trúc; nội dung mỏng, khóa, chỉ có PDF; không ngày, không tác giả.
- **Được trích ≠ được giới thiệu.** Lọt danh sách đề xuất phụ thuộc đồng thuận trên toàn web (đánh giá, diễn đàn, báo chí). Bài "top [ngành]" tự quảng bá có thể phản tác dụng với thương hiệu mới (AI trích bài của bạn nhưng giới thiệu đối thủ).

## Theo dõi

| Chỉ số | Cách kiểm |
|---|---|
| Có AI Overview cho truy vấn của bạn không | Thủ công hoặc Semrush/Ahrefs |
| Tỷ lệ được trích dẫn | Công cụ theo dõi AI |
| Thị phần tiếng nói trên AI so với đối thủ | Peec AI, Otterly, ZipTie, Omnia, Profound, Ahrefs Brand Radar |
| Sắc thái AI mô tả thương hiệu | Đọc thủ công + công cụ |
| Tỷ lệ được giới thiệu | Theo dõi prompt + cách nhắc tên |
| Nguồn và tác động | Lượt giới thiệu từ AI + tìm kiếm thương hiệu, truy cập trực tiếp bị trễ ([ai-attribution.md](references/ai-attribution.md)) |

**Tự làm không công cụ (hằng tháng):** chọn 20 truy vấn → chạy trên ChatGPT, Gemini, Google → ghi: có được trích không, ai được, trang nào → theo dõi theo tháng. Câu trả lời AI **không tất định**: một lần chạy chỉ là giai thoại. Chạy mỗi truy vấn 3–5 lần mỗi nền tảng, ghi tỷ lệ kèm cỡ mẫu ("được trích 3/5"). Search Console không có báo cáo riêng cho AI.

## Những điều KHÔNG làm

1. Viết nội dung riêng "cho AI" (rủi ro chính sách lạm dụng nội dung quy mô lớn)
2. Băm trang thành mảnh vụn để mồi AI
3. Tạo nội dung hàng loạt để thao túng thứ hạng
4. Tạo nhắc tên giả: bịa trích dẫn, giải thưởng, tự lập trang "đánh giá độc lập", spam diễn đàn/Wikipedia; đánh giá giả còn vi phạm quy định bảo vệ người tiêu dùng
5. Coi mọi bot AI như một
6. Giấu nội dung chính sau JavaScript không hiển thị
7. Bỏ qua nền tảng E-E-A-T

Hướng dẫn theo loại nội dung (trang sản phẩm, blog, so sánh, tài liệu, địa phương/TMĐT): [content-types.md](references/content-types.md). Nội dung đa ngôn ngữ (Việt – Anh): [multilingual-and-commerce.md](references/multilingual-and-commerce.md).

## Lỗi thường gặp

Bỏ qua tìm kiếm AI; tách AI SEO khỏi SEO; viết cho AI thay vì cho người; không có tín hiệu độ mới; khóa toàn bộ nội dung; bỏ qua hiện diện bên thứ ba; không có dữ liệu có cấu trúc; nhồi từ khóa; giấu giá; chặn crawler khám phá mà không xét mục đích; nội dung chung chung không số liệu ("chúng tôi tốt nhất" — vừa không được trích, vừa có thể vi phạm luật quảng cáo); không theo dõi.

## Công cụ

Có kết nối thì dùng: Semrush, Ahrefs (theo dõi AI Overview, nghiên cứu từ khóa), Google Search Console, GA4 (lượt giới thiệu từ nguồn AI). Danh mục: [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md).

## Skill liên quan

- `seo-audit` — SEO kỹ thuật và on-page truyền thống
- `link-building`, `public-relations` — liên kết và nhắc tên trên các trang AI trích
- `schema` — dữ liệu có cấu trúc
- `content-strategy` — kế hoạch nội dung
- `competitors` — nội dung so sánh (lưu ý pháp lý Việt Nam)
- `local-marketing` — Google Business Profile cho tìm kiếm AI địa phương
- `copywriting` — viết vừa dễ đọc cho người vừa dễ trích cho AI
