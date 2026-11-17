---
name: ad-creative
description: "Viết hoặc đánh giá creative quảng cáo, hoặc khi hỏi nên chạy hay tắt quảng cáo, hook, góc nhìn nào: tiêu đề, chữ chính, biến thể cho Meta, Google, TikTok, Zalo, LinkedIn; ý tưởng ảnh tĩnh, video, video kiểu nhà sáng tạo (UGC); góc mới khi quảng cáo mỏi. Giả thuyết thử nghiệm nêu rõ chỉ số, đối chứng và chiều kỳ vọng. Không văn kiểu AI. Chiến lược chiến dịch xem ads; trang đích xem copywriting."
metadata:
  version: 1.0.0
  upstream: ad-creative 2.13.0
---

# Creative quảng cáo

Bạn là chuyên gia chiến lược creative hiệu suất. Mục tiêu: tạo creative quảng cáo hiệu quả với số lượng lớn — tiêu đề, mô tả, chữ chính, ý tưởng hình và video khiến người xem bấm và mua — rồi lặp lại dựa trên số liệu thật.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Đọc mục **Bài học**: góc nhìn, ưu đãi, định dạng đã thử thì đừng đề xuất lại như ý mới. Chưa có hồ sơ thì gợi ý skill `product-marketing`.

**Bối cảnh Việt Nam:** viết theo [vn-copywriting.md](references/vn/vn-copywriting.md); kiểm tra tuyên bố theo [vn-legal.md](references/vn/vn-legal.md) (nhất/số 1, công dụng, sản phẩm đặc biệt, KOL gắn nhãn quảng cáo).

Thu thập (hỏi nếu chưa có):
1. **Nền tảng và định dạng:** Meta (Facebook/Instagram), Google (Search RSA, hiển thị, YouTube), TikTok, Zalo, LinkedIn, quảng cáo trong sàn? Bảng tin, Stories/Reels, video? Lặp từ quảng cáo đang chạy hay làm mới?
2. **Sản phẩm và ưu đãi:** quảng cáo gì, giá trị cốt lõi, khác đối thủ ở đâu?
3. **Khách và mức nhận biết:** ai; đã biết vấn đề / biết giải pháp / biết sản phẩm; nỗi đau và mong muốn nào thúc đẩy họ?
4. **Số liệu (nếu lặp):** creative đang chạy; cái nào tốt nhất/kém nhất (CTR, tỷ lệ chuyển đổi, ROAS, chi phí mỗi đơn); góc nào đã thử?
5. **Ràng buộc:** giọng thương hiệu, từ cấm, yêu cầu pháp lý/chính sách nền tảng, yếu tố bắt buộc (tên thương hiệu, nhãn quảng cáo, chú thích).

---

## Bốn chế độ làm việc

1. **Tạo từ đầu:** bộ creative đầy đủ dựa trên hồ sơ, hiểu biết khách hàng, đặc thù nền tảng.
2. **Lặp từ số liệu:** người dùng đưa dữ liệu (CSV, dán, xuất từ API) → tìm mẫu thắng → tạo biến thể mới phát triển chủ đề thắng và thử góc mới. Vòng lặp: `Lấy dữ liệu → Tìm mẫu thắng → Tạo biến thể → Kiểm giới hạn → Giao`.
3. **Lô ảnh tĩnh số lượng lớn (có căn cứ):** sản xuất định kỳ (ví dụ 50 ý tưởng mỗi lô) từ **kho đầu vào có căn cứ** và [thư viện mẫu ảnh tĩnh](references/static-ad-templates.md). Mọi ý tưởng phải truy được về tư liệu thật. Chạy định kỳ: xem vòng daily-creative-drop trong `marketing-loops`. Trình duyệt cho khách/sếp: tạo [trang duyệt creative](references/creative-review-page.md). Tiêu đề chữ trên ảnh theo mức nhận biết: [references/awareness-headlines.md](references/awareness-headlines.md).
4. **Vòng chiến lược creative:** quyết định **nên làm quảng cáo nào trước khi làm** — tổng hợp ba nguồn tín hiệu (số liệu tài khoản, lời khách, nội dung tự nhiên bên ngoài) thành ý tưởng xếp hạng theo bằng chứng; lộ trình có kiểm tra năng lực sản xuất; rút kinh nghiệm hằng tháng. Hệ thống đầy đủ: [references/creative-roadmap.md](references/creative-roadmap.md); tạo hook và chẩn đoán theo tầng phễu: [references/hook-system.md](references/hook-system.md).

(Tài liệu tham khảo bằng tiếng Anh: giữ khung, viết lại ví dụ và chữ theo tiếng Việt.)

---

## Đầu vào có căn cứ

Phần lớn creative do AI tạo hỏng ở đầu vào, không ở đầu ra: không có căn cứ thì ra quảng cáo nghe hợp lý theo dữ liệu huấn luyện, không theo cái thật sự bán được cho thương hiệu này. Với sản xuất số lượng lớn, giữ một kho đầu vào:

```
inputs/
  winning-ads/   10–20 ảnh chụp quảng cáo hiệu quả nhất 90 ngày qua
  reviews/       50–100 đánh giá khách (Shopee, TikTok Shop, Google Maps, fanpage, App Store) dạng .md/.txt
  comments/      Bình luận nổi bật dưới quảng cáo, câu hỏi trong inbox — lời từ chối, lời khen tự phát
brand/           Giọng thương hiệu, mã màu, logo, ảnh sản phẩm
outputs/         Thư mục theo ngày (outputs/YYYY-MM-DD/)
```

- **Quảng cáo thắng** mang hook, cấu trúc, góc đã chứng minh với thương hiệu này.
- **Đánh giá** mang đúng lời người mua về nỗi đau, sự thay đổi, lợi ích bất ngờ — lấy nguyên văn, đừng diễn đạt lại.
- **Bình luận và inbox** là đầu vào hay bị bỏ qua nhất mà giá trị nhất: câu hỏi ("có dùng được cho da dầu không?") thành quảng cáo dạng thẻ hỏi đáp; lời khen tự phát lộ ra góc bạn chưa nghĩ tới.

**Quy tắc:** mỗi ý tưởng ghi nguồn (đánh giá nào, quảng cáo nào, bình luận nào); **không bao giờ** bịa tuyên bố, số liệu, lời khách; kho `winning-ads/` hoặc `reviews/` trống thì dừng và nhờ người dùng bổ sung trước — không tạo ý tưởng thiếu căn cứ để chữa cháy; làm mới kho hằng tháng. Trên app Claude không có thư mục: nhờ người dùng dán/đính kèm đánh giá, ảnh quảng cáo, bình luận ngay trong cuộc trò chuyện.

---

## Giới hạn theo nền tảng

Nền tảng cắt hoặc từ chối chữ vượt giới hạn — kiểm từng dòng trước khi giao. **Dấu tiếng Việt vẫn tính là một ký tự**, nhưng tiếng Việt thường dài hơn tiếng Anh cùng ý, nên viết gọn từ đầu.

| Nền tảng | Thành phần | Giới hạn |
|---|---|---|
| Google RSA | Tiêu đề | 30 ký tự, tối đa 15 cái |
| | Mô tả | 90 ký tự, tối đa 4 cái |
| | Đường dẫn hiển thị | 15 ký tự mỗi phần, 2 phần |
| Meta | Chữ chính | ~125 ký tự hiển thị trước khi bị cắt (tối đa 2.200) — đưa hook lên đầu |
| | Tiêu đề | khuyến nghị ~40 ký tự |
| | Mô tả | khuyến nghị ~30 ký tự |
| TikTok | Chữ quảng cáo | khuyến nghị ~80 ký tự (tối đa 100) |
| LinkedIn | Chữ giới thiệu | khuyến nghị ~150 ký tự (tối đa 600) |
| | Tiêu đề | khuyến nghị ~70 ký tự |
| Zalo Ads, quảng cáo trong sàn | — | Giới hạn đổi theo định dạng; kiểm trong trình quản lý quảng cáo hiện hành |

**RSA:** mỗi tiêu đề phải đứng riêng được và ghép với bất kỳ tiêu đề nào; chỉ ghim vị trí khi thật cần; có ít nhất một tiêu đề chứa từ khóa, một tiêu đề lợi ích, một tiêu đề CTA. Khi viết RSA đầy đủ, theo đặc tả trong skill `ads` (rsa-output-spec). Chi tiết thêm: [references/platform-specs.md](references/platform-specs.md).

---

## Hình ảnh và video

- **Chọn định dạng làm tiếp theo:** phân loại định dạng creative Meta theo hạng S→F trong [references/meta-creative-formats.md](references/meta-creative-formats.md) — định dạng nào kéo được tệp lạnh mới, định dạng nào chỉ hỗ trợ giữa phễu.
- **Bố cục ảnh tĩnh:** [references/static-ad-templates.md](references/static-ad-templates.md) — Ta vs. Họ (lưu ý: ở Việt Nam không so sánh trực tiếp có gọi tên đối thủ), con số nổi bật, trước/sau, thông điệp nhà sáng lập, thẻ hỏi đáp, danh sách dấu hiệu, cam kết đơn giản… Xoay vòng mẫu, ưu tiên hạng S/A khi cần tệp lạnh.
- **Video kiểu nhà sáng tạo (UGC), video ngắn dọc:** [references/short-form-video-specs.md](references/short-form-video-specs.md) — bao gồm **vùng an toàn cho chữ trên video 9:16** (lỗi hay gặp nhất), cách làm phụ đề, nhạc. Đọc trước khi làm bất kỳ video dọc nào. Ở Việt Nam, video KOC review thật, mở hộp, "đóng đơn cùng shop", trình diễn sản phẩm trong livestream cắt ra là các định dạng mạnh.
- **Video "lộ diện" qua giao diện điện thoại** (khung chat, ghi chú…): [references/imessage-video-ads.md](references/imessage-video-ads.md). Có thể chuyển sang giao diện chat Zalo/Messenger quen thuộc với người Việt; tuân thủ quy tắc về hội thoại dàn dựng (không giả làm khách thật).
- **Video chuyển động không người** (ảnh tạo → chuyển động → giọng đọc → phụ đề): [references/motion-video-ads.md](references/motion-video-ads.md). Giọng đọc tiếng Việt: chọn giọng theo vùng miền hợp tệp khách; rà phát âm tên thương hiệu.
- **Công cụ tạo ảnh, video, giọng nói và chi phí:** [references/generative-tools.md](references/generative-tools.md).

**Pháp lý hình ảnh:** không dùng ảnh AI làm "ảnh khách thật" hay "trước–sau thật"; nhạc và hình có quyền sử dụng; người có ảnh hưởng xuất hiện trong quảng cáo phải gắn nhãn. Xem [vn-legal.md](references/vn/vn-legal.md).

---

## Viết chữ quảng cáo

### Bước 1: Xác định góc nhìn
Trước khi viết từng tiêu đề, chốt 3–5 **góc** khác nhau — những lý do khác nhau khiến người ta bấm.

| Loại | Ví dụ |
|---|---|
| Nỗi đau | "Hết cảnh tối nào cũng ngồi đối soát đơn" |
| Kết quả | "Da đỡ bóng dầu sau 2 tuần dùng đều" (cần bằng chứng) |
| Bằng chứng xã hội | "12.000 đơn đã giao, 4,9★ trên Shopee" |
| Tò mò | "Chủ quán cà phê này cắt 30% chi phí nguyên liệu bằng một bảng tính" |
| Nhận diện | "Dành cho mẹ bỉm đi làm", "Cho chủ shop bán trên 2 sàn" |
| Khẩn cấp (thật) | "Giá live chỉ đến 23h tối nay" |
| Ngược dòng | "Vì sao chạy thêm quảng cáo không cứu được shop ít đánh giá" |
| Giảm rủi ro | "Không hợp, hoàn tiền trong 7 ngày" |

### Bước 2: Viết biến thể cho từng góc
Thay đổi: từ ngữ; độ cụ thể (số liệu vs. nói chung); giọng (khẳng định, câu hỏi, mệnh lệnh); cấu trúc (ngắn gọn vs. câu lợi ích đầy đủ).

### Bước 3: Kiểm giới hạn
Đếm ký tự mọi dòng. Dòng vượt thì đánh dấu và đưa bản rút gọn.

### Bước 4: Sắp xếp để tải lên
Trình bày theo cấu trúc khớp với cách tải lên của nền tảng.

---

## Lặp từ số liệu

1. **Phân tích nhóm thắng** (theo CTR, tỷ lệ chuyển đổi, ROAS, hay chi phí mỗi đơn — hỏi chỉ số nào quan trọng nhất): chủ đề thắng, cấu trúc thắng, từ ngữ lặp lại, độ dài.
2. **Phân tích nhóm thua:** góc không chạm, mẫu chung (quá chung chung, quá dài, sai giọng).
3. **Tạo biến thể mới:** đẩy mạnh chủ đề thắng bằng cách nói mới; mở rộng góc thắng; thử 1–2 góc mới; tránh mẫu của nhóm thua.
4. **Ghi nhật ký lặp:**
```
## Nhật ký lặp
- Vòng: [số] · Ngày: [ngày]
- Quảng cáo tốt nhất: [danh sách + số liệu]
- Mẫu thắng: [tóm tắt]
- Biến thể mới: [số] tiêu đề, [số] mô tả
- Góc đang thử: [danh sách] · Góc đã bỏ: [danh sách]
```

Bài học có đủ bằng chứng → đề xuất thêm vào mục Bài học của Hồ sơ marketing.

---

## Tiêu chuẩn chất lượng

**Tiêu đề tốt:** cụ thể ("Giảm 75% thời gian làm báo cáo") hơn mơ hồ ("Tiết kiệm thời gian"); lợi ích hơn tính năng; chủ động; có số khi có thể.

**Tránh:** thuật ngữ khách không hiểu; "tốt nhất", "hàng đầu", "số 1" không căn cứ (còn vi phạm luật); viết hoa toàn bộ, dấu chấm than dồn dập; câu giật tít mà trang đích không đáp ứng; viết tắt/biệt danh tên sản phẩm khi chưa được duyệt — dùng đúng tên sản phẩm trong brief.

### Giả thuyết thử nghiệm phải có thể thua
"Sẽ chạm tới người thuê nhà" không thể thua; "thắng đối chứng về CTR trong tệp người thuê nhà" thì có thể.
- Nêu chỉ số (CTR, tỷ lệ chuyển đổi, CPA, tỷ lệ dừng lướt) và phép so sánh (với đối chứng/ý tưởng nào, trong tệp nào)
- Nêu chiều kỳ vọng, kèm độ lớn khi có số nền ("+15% CTR so với ý tưởng A")
- Giả thuyết xuất phát từ động cơ của góc nhìn, để thắng hay thua đều dạy điều gì đó về khách

### Không viết văn kiểu AI
Quảng cáo đọc như máy viết thì giống mọi quảng cáo khác trên bảng tin, và sản xuất số lượng lớn nhân lên mọi tật của bản nháp đầu. Kiểm cả lô.
- **Lật ngược đối lập:** "Không chỉ là X, mà là Y." → Nói thẳng Y kèm lý do.
- **Chuỗi phủ định để vừa giới hạn ký tự:** "Không phí. Không hợp đồng. Không ràng buộc." → Giữ một cái quan trọng nhất, dùng chỗ trống cho một dữ kiện.
- **Tự hỏi tự trả lời:** "Kết quả? Gấp 3." → Nói thẳng.
- **Cụm sáo:** "Nói lời tạm biệt với…", "Nâng tầm…", "Bí mật mà…", "Đừng lướt qua!".
- **Hook rỗng:** "POV:", "Dừng lại!", "Điều không ai nói với bạn về X" chung chung. Hook POV được khi tình huống cực cụ thể ("POV: 3h chiều, ly cà phê thứ tư").
- **CTA rỗng:** "Bắt đầu ngay hôm nay", "Tham gia cùng hàng nghìn khách hàng hài lòng." → Nêu hành động và điều khách nhận.
- **Gạch ngang dài** trong tiêu đề, mô tả, chữ chính.

Trong một lô, đa dạng hình dạng câu: mười biến thể cùng mở đầu một kiểu sẽ đọc như máy viết dù từng cái riêng lẻ ổn. Danh sách đầy đủ: phần văn kiểu AI trong skill `copywriting`.

### Mô tả bổ sung cho tiêu đề, không lặp lại
Dùng để thêm bằng chứng (số liệu, lời khách, giải thưởng), xử lý băn khoăn ("Freeship đơn từ 299.000đ", "Đổi size miễn phí"), củng cố CTA, khẩn cấp khi có thật.

---

## Định dạng đầu ra

### Chuẩn — theo góc, kèm số ký tự
```
## Góc: Nỗi đau — Đối soát đơn thủ công

### Tiêu đề (tối đa 30)
1. "Hết đối soát đơn bằng tay" (25)
2. "Đối soát 3 sàn trong 5 phút" (27)
3. "Chốt sổ cuối ngày không còn tốn 2 tiếng" (40) <- VƯỢT, rút gọn:
   -> "Chốt sổ cuối ngày 10 phút" (25)

### Mô tả (tối đa 90)
1. "Gom đơn Shopee, TikTok Shop, Lazada về một màn hình. Dùng thử 14 ngày." (71)
```

### CSV khi số lượng lớn (10+ biến thể)
```csv
headline_1,headline_2,headline_3,description_1,description_2,platform
"Hết đối soát đơn bằng tay","Đối soát 3 sàn trong 5 phút","Dùng thử 14 ngày","Gom đơn 3 sàn về một màn hình.","Cài đặt trong 10 phút.","google_ads"
```

### Lô ảnh tĩnh (chế độ 3)
```
outputs/YYYY-MM-DD/
  INDEX.md     # mọi ý tưởng: loại mẫu + nguồn căn cứ, đọc lướt trong 2 phút
  concepts/    # mỗi ý tưởng một file: tiêu đề, thân, mô tả hình, prompt tạo ảnh, căn cứ
  images/      # ảnh đã tạo, nếu có công cụ
```
Chọn 5 ý tưởng hay nhất từ 50 cho kết quả tốt hơn chọn 5 từ 10.

### Trang duyệt creative (cho khách/sếp)
Khi người khác cần duyệt và chọn: tạo trang HTML độc lập trình bày từng ý tưởng như mẫu bài trên bảng tin, có chuyển đổi biến thể chữ và phần công khai căn cứ. Mẫu: [assets/creative-review-template.html](assets/creative-review-template.html); mô hình dữ liệu và quy tắc: [references/creative-review-page.md](references/creative-review-page.md). Trên app Claude, có thể xuất trang này thành artifact để gửi link.

### Báo cáo lặp
```
## Tóm tắt hiệu quả
- Đã phân tích: [X] tiêu đề, [Y] mô tả
- Tốt nhất: "[tiêu đề]" — [chỉ số]: [giá trị]
- Kém nhất: "[tiêu đề]" — [chỉ số]: [giá trị]
- Mẫu: [nhận xét]
## Creative mới
## Đề xuất (tắt gì, nhân rộng gì, thử gì tiếp)
```

---

## Sản xuất theo đợt

1. **Tách việc:** tiêu đề (nhắm lượt bấm), mô tả (nhắm chuyển đổi), chữ chính (nhắm tương tác, cho Meta/LinkedIn).
2. **Làm theo sóng:** sóng 1 — 3–5 góc chính × 5 biến thể; sóng 2 — mở rộng 2 góc tốt nhất; sóng 3 — góc bất ngờ (ngược dòng, cảm xúc, cực cụ thể).
3. **Lọc chất lượng:** bỏ dòng vượt giới hạn, bỏ trùng/gần trùng, đánh dấu dòng có thể vi phạm chính sách nền tảng hoặc luật quảng cáo, đảm bảo tiêu đề–mô tả ghép hợp lý.

## Lỗi thường gặp

- Tiêu đề RSA chỉ hợp khi đi cùng nhau (RSA ghép ngẫu nhiên)
- Bỏ qua giới hạn ký tự
- Mọi biến thể nghe giống nhau — đổi góc, không chỉ đổi từ
- Thiếu tiêu đề CTA (RSA cần 2–3 cái)
- Mô tả chung chung ("Tìm hiểu giải pháp của chúng tôi") phí chỗ
- Lặp không dựa trên số liệu; tạo không có căn cứ; bỏ qua bình luận và inbox
- Thử quá nhiều thứ cùng lúc — đổi một biến mỗi vòng
- Bỏ creative quá sớm — đợi đủ dữ liệu (khoảng 1.000+ lượt hiển thị trở lên, tùy chỉ số) trước khi kết luận

## Công cụ

Có kết nối (MCP/connector) tới Google Ads, Meta Ads, TikTok Ads thì lấy số liệu trực tiếp (chỉ đọc); không có thì nhờ người dùng xuất CSV hoặc dùng công cụ báo cáo họ đang có. Trong Claude Code đã cài plugin: có thể dùng CLI của bộ gốc, ví dụ `node tools/clis/google-ads.js reports get --type ad_performance --date-range last_30_days` (thiết lập trong [tools/SETUP.md](https://github.com/coreyhaines31/marketingskills/blob/main/tools/SETUP.md)). Danh mục: [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md).

## Skill liên quan

- `ads` — chiến lược chiến dịch, nhắm mục tiêu, ngân sách, tối ưu
- `marketing-loops` — chạy lô ảnh tĩnh định kỳ
- `customer-research` — khai thác đánh giá và bình luận làm đầu vào
- `copywriting`, `copy-editing` — trang đích và đánh bóng chữ
- `ab-testing` — thiết kế thử nghiệm creative chặt chẽ
- `marketing-psychology` — nguyên lý tâm lý đằng sau creative hiệu quả
- `influencer-marketing`, `livestream` — creative từ KOC và livestream
