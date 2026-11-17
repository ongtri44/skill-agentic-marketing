---
name: product-marketing
description: "Lập hoặc cập nhật Hồ sơ marketing sản phẩm, tài liệu nền mà mọi skill marketing khác đọc trước: sản phẩm, khách hàng mục tiêu (ICP), định vị, đối thủ, ngôn ngữ khách hàng, giọng thương hiệu và cách xưng hô, kênh bán. Dùng đầu tiên khi bắt đầu dự án mới, khi đổi tệp khách hoặc định vị, khi hỏi hồ sơ cần gì, định vị đã đủ rõ chưa, hoặc để ghi lại bài học từ chiến dịch."
metadata:
  version: 1.0.0
  upstream: product-marketing 2.2.3
---

# Hồ sơ marketing sản phẩm

Bạn giúp người dùng lập và duy trì **Hồ sơ marketing**: một tài liệu ghi lại định vị, khách hàng, thông điệp và giọng thương hiệu. Mọi skill marketing khác trong bộ đọc hồ sơ này trước khi làm việc, nên người dùng không phải giải thích lại từ đầu mỗi lần.

## Hồ sơ nằm ở đâu

Cách lưu phụ thuộc nơi bạn đang chạy:

| Môi trường | Nơi lưu hồ sơ |
|---|---|
| **Claude Code / agent có thư mục dự án** | File `.agents/product-marketing.md` trong thư mục dự án |
| **App Claude (web, desktop, điện thoại)** | Không có file lưu lâu dài giữa các cuộc trò chuyện. Tạo hồ sơ hoàn chỉnh, rồi hướng dẫn người dùng lưu vào **Project**: thêm vào phần kiến thức (knowledge) hoặc hướng dẫn của Project. Mọi cuộc trò chuyện trong Project đó sẽ đọc được. Nếu có công cụ tạo tài liệu (artifact, Docs), lưu hồ sơ thành tài liệu để người dùng giữ và sửa. |

Khi tìm hồ sơ đã có, kiểm tra theo thứ tự: `.agents/product-marketing.md`; `.claude/product-marketing.md`; tên cũ `product-marketing-context.md` (trong `.agents/` hoặc `.claude/`); tài liệu tên "Hồ sơ marketing" hoặc "Product Marketing Context" trong kiến thức của Project; nội dung người dùng dán vào cuộc trò chuyện. Nếu thấy file ở vị trí cũ, đề nghị chuyển về `.agents/product-marketing.md`.

## Quy trình

### Bước 1: Kiểm tra hồ sơ hiện có

**Nếu đã có:**
- Đọc và tóm tắt những gì đã có, kèm **phiên bản hồ sơ** và vài dòng **Nhật ký thay đổi** gần nhất để người dùng thấy hồ sơ đang ở đâu.
- Hỏi người dùng muốn cập nhật phần nào; chỉ thu thập thông tin cho phần đó.
- Mỗi lần lưu thay đổi có nội dung: tăng phiên bản và thêm dòng nhật ký (xem Bước 4).

**Nếu chưa có, đề nghị hai cách:**

1. **Tự soạn bản nháp từ tài liệu có sẵn** (khuyến nghị): website, fanpage, trang gian hàng trên sàn, hồ sơ năng lực, bảng giá, kịch bản tư vấn, mã nguồn (README, trang đích) — bất cứ thứ gì người dùng đưa hoặc bạn đọc được. Soạn bản v1 rồi để người dùng sửa và bổ sung. Nhanh hơn nhiều so với hỏi từ đầu.
2. **Hỏi từng phần:** đi qua các mục bên dưới bằng hội thoại, mỗi lần một mục.

Phần lớn người dùng chọn cách 1. Sau khi đưa bản nháp, hỏi: "Chỗ nào sai? Còn thiếu gì?"

### Bước 2: Thu thập thông tin

**Nếu tự soạn:**
1. Đọc tài liệu có sẵn: website, mô tả sản phẩm, bài đăng, đánh giá khách hàng, bảng giá, kịch bản tư vấn, tài liệu bán hàng, mã nguồn nếu có.
2. Soạn tất cả các mục dựa trên những gì tìm được; mục nào không có dữ liệu thì để trống và đánh dấu "cần bổ sung".
3. Đưa bản nháp và hỏi chỗ cần sửa.
4. Sửa đến khi người dùng hài lòng.

**Nếu hỏi từng phần:** đừng hỏi dồn mọi câu một lúc. Với mỗi mục: giải thích ngắn mục này ghi gì → hỏi → xác nhận lại → sang mục tiếp.

**Xin nguyên văn lời khách hàng.** Câu chữ khách thật sự dùng (trong inbox, đánh giá trên sàn, bình luận, cuộc gọi tư vấn) giá trị hơn mô tả trau chuốt, vì nó phản ánh cách khách nghĩ và nói — viết quảng cáo bằng chính lời đó sẽ chạm hơn.

---

## Các mục cần ghi

### 1. Tổng quan sản phẩm
- Mô tả một câu
- Sản phẩm làm gì (2–3 câu)
- Ngành hàng / "kệ" mà khách tìm bạn (khách gõ gì để tìm ra bạn)
- Loại hình: bán lẻ, TMĐT, F&B, dịch vụ, phần mềm, B2B, nhượng quyền…
- Mô hình kinh doanh và giá

### 2. Khách hàng mục tiêu
- **B2C:** độ tuổi, giới tính, thu nhập, khu vực (thành phố/tỉnh, nội thành/ngoại thành), hoàn cảnh sống
- **B2B:** loại doanh nghiệp (ngành, quy mô, giai đoạn), người ra quyết định (vai trò, phòng ban)
- Nhu cầu chính (vấn đề lớn nhất bạn giải quyết)
- Việc khách "thuê" sản phẩm làm (2–3 việc)
- Tình huống sử dụng cụ thể

### 3. Các vai trò trong quyết định mua (chủ yếu B2B, hoặc B2C có người mua khác người dùng)
Nếu nhiều người cùng quyết định, ghi cho từng người: người dùng, người ủng hộ, người quyết định, người duyệt chi, người tư vấn kỹ thuật — mỗi người quan tâm gì, khó khăn gì, bạn hứa giá trị gì. Với B2C: ví dụ mẹ mua cho con, con mua biếu bố mẹ.

### 4. Vấn đề và nỗi đau
- Khó khăn cốt lõi của khách trước khi gặp bạn
- Vì sao cách hiện tại chưa ổn
- Họ tốn gì (thời gian, tiền, cơ hội)
- Căng thẳng cảm xúc (lo lắng, sợ mua phải hàng giả, ngại bị chê…)

### 5. Bức tranh cạnh tranh
- **Đối thủ trực tiếp:** cùng giải pháp, cùng vấn đề
- **Đối thủ gián tiếp:** khác giải pháp, cùng vấn đề (ví dụ: chuỗi cà phê vs cà phê pha sẵn ở nhà)
- **Cách khách tự xoay xở:** làm thủ công, nhờ người quen, mua chợ, không làm gì
- Mỗi lựa chọn hụt ở đâu với khách

### 6. Khác biệt
- Điểm khác biệt chính (thứ lựa chọn khác không có)
- Bạn giải quyết khác thế nào
- Vì sao như vậy tốt hơn (lợi ích)
- Vì sao khách chọn bạn

### 7. Lời từ chối thường gặp và khách không phù hợp
- 3 lời từ chối hay gặp nhất khi tư vấn/bán và cách trả lời
- Ai **không** phải khách phù hợp

### 8. Động lực chuyển đổi (bốn lực JTBD)
- **Đẩy:** điều gì làm họ chán cách cũ
- **Kéo:** điều gì hút họ về phía bạn
- **Thói quen:** điều gì giữ họ ở lại cách cũ
- **Lo lắng:** điều gì khiến họ ngại đổi

### 9. Ngôn ngữ khách hàng
- Khách mô tả vấn đề thế nào (nguyên văn)
- Khách mô tả bạn thế nào (nguyên văn)
- Từ nên dùng / từ tránh dùng
- Bảng thuật ngữ riêng của sản phẩm

### 10. Giọng thương hiệu và xưng hô
- **Xưng hô:** thương hiệu xưng gì, gọi khách là gì, theo từng kênh (bài đăng, inbox, livestream, email). Xem [vn-copywriting.md](references/vn/vn-copywriting.md).
- 3–5 tính cách giọng văn, mỗi cái kèm: nghĩa là gì, không có nghĩa là gì, một câu thật từ nội dung đã dùng
- Giọng theo ngữ cảnh: chăm sóc khách, ra mắt, báo lỗi, bán hàng, mạng xã hội
- Từ thương hiệu sở hữu; từ không bao giờ dùng (kèm lý do)

Xây giọng văn từ nội dung đã từng hiệu quả và cách chủ doanh nghiệp tự viết, đừng từ vài tính từ chọn trong buổi họp. Xem [references/brand-voice.md](references/brand-voice.md) (tiếng Anh) để biết các bước rút giọng văn, ví dụ mẫu và hướng dẫn giọng cho từng người.

### 11. Kênh bán và vận hành (Việt Nam)
- Kênh đang bán: website, sàn (Shopee, TikTok Shop, Lazada, Tiki), fanpage, Zalo OA, cửa hàng, đại lý, sales trực tiếp
- Khu vực phục vụ, thời gian giao, phí ship, đổi trả
- Thanh toán: COD, chuyển khoản, ví, thẻ, trả góp
- Mùa cao điểm của ngành (xem lịch trong [vn-market.md](references/vn/vn-market.md))

### 12. Pháp lý sản phẩm
- Sản phẩm có thuộc nhóm đặc biệt không (thực phẩm, thực phẩm bảo vệ sức khỏe, mỹ phẩm, thuốc, thiết bị y tế, dịch vụ y tế, giáo dục, tài chính…)?
- Giấy phép, công bố, chứng nhận đang có; những tuyên bố công dụng được phép nói
- Những câu không được nói. Xem [vn-legal.md](references/vn/vn-legal.md).

### 13. Bằng chứng
- Số liệu, kết quả có thể trích dẫn (kèm nguồn)
- Khách hàng, đối tác tiêu biểu; số đã bán; điểm đánh giá trên sàn
- Trích lời khách hàng (đã được phép dùng)
- Các chủ đề giá trị chính và bằng chứng cho từng chủ đề

### 14. Mục tiêu
- Mục tiêu kinh doanh chính
- Hành động chuyển đổi chính (đặt hàng, để lại số điện thoại, nhắn Zalo, đặt lịch, đăng ký dùng thử…)
- Số liệu hiện tại (nếu có)

### 15. Quảng cáo trả phí (chỉ khi có chạy quảng cáo)
Skill `ads` đọc mục này để người dùng không phải giải thích lại tài khoản mỗi lần.
- Ngưỡng lãi: CPA hoặc ROAS mục tiêu để có lãi, và mức sàn (ROAS dưới mức này hoặc CPA trên mức này thì báo ngay)
- Ngân sách: ngân sách tháng, mức dao động ngày chấp nhận được
- Chuyển đổi thật: hành động nào được tính và đáng bao nhiêu; điểm yếu đo lường đã biết (độ trễ, đếm trùng, đơn COD bị hủy, đơn chốt qua inbox không đo được); thế nào là lead tốt và thế nào chỉ là điền form
- Quy ước đặt tên chiến dịch và mục đích từng chiến dịch, mỗi chiến dịch một dòng
- Việc Claude được làm (đọc, so sánh, cảnh báo, soạn nháp, đề xuất) và không được làm khi chưa duyệt (đổi ngân sách/giá thầu, tắt/bật, sửa đo lường, đăng quảng cáo)

### 16. Bài học
Để trống lúc đầu. Mục này đầy dần khi chạy chiến dịch (xem "Ghi bài học" bên dưới).

---

## Bước 3: Tạo hồ sơ

Sau khi thu thập đủ, tạo hồ sơ theo mẫu sau. Mục nào không áp dụng thì bỏ.

```markdown
# Hồ sơ marketing — [Tên thương hiệu]

**Phiên bản:** v1
**Cập nhật lần cuối:** [ngày]

## Tổng quan sản phẩm
**Một câu:**
**Làm gì:**
**Ngành hàng / kệ:**
**Loại hình:**
**Mô hình kinh doanh và giá:**

## Khách hàng mục tiêu
**Chân dung:**
**Người ra quyết định:**
**Nhu cầu chính:**
**Việc khách thuê sản phẩm làm:**
-
**Tình huống sử dụng:**
-

## Vai trò trong quyết định mua
| Vai trò | Quan tâm | Khó khăn | Giá trị ta hứa |
|---|---|---|---|
| | | | |

## Vấn đề và nỗi đau
**Vấn đề cốt lõi:**
**Vì sao cách hiện tại chưa ổn:**
-
**Họ tốn gì:**
**Căng thẳng cảm xúc:**

## Cạnh tranh
**Trực tiếp:** [Đối thủ] — hụt ở…
**Gián tiếp:** [Cách khác] — hụt ở…
**Tự xoay xở:** [Cách khách tự làm] — hụt ở…

## Khác biệt
**Điểm khác biệt chính:**
-
**Cách ta làm khác:**
**Vì sao tốt hơn:**
**Vì sao khách chọn ta:**

## Lời từ chối
| Lời từ chối | Cách trả lời |
|---|---|
| | |

**Khách không phù hợp:**

## Động lực chuyển đổi
**Đẩy:**
**Kéo:**
**Thói quen:**
**Lo lắng:**

## Ngôn ngữ khách hàng
**Khách mô tả vấn đề:**
- "[nguyên văn]"
**Khách mô tả ta:**
- "[nguyên văn]"
**Từ nên dùng:**
**Từ tránh dùng:**
**Thuật ngữ:**
| Từ | Nghĩa |
|---|---|
| | |

## Giọng thương hiệu
**Xưng hô:** thương hiệu xưng "…", gọi khách "…" (bài đăng: … / inbox: … / livestream: … / email: …)
| Tính cách | Nghĩa là | Không có nghĩa là | Câu ví dụ |
|---|---|---|---|
| | | | |

**Giọng theo ngữ cảnh:**
- Chăm sóc khách:
- Ra mắt:
- Báo lỗi:
- Bán hàng:
- Mạng xã hội:
**Từ ta sở hữu:**
**Không bao giờ dùng (và lý do):**

## Kênh bán và vận hành
**Kênh:**
**Khu vực, giao hàng, đổi trả:**
**Thanh toán:**
**Mùa cao điểm:**

## Pháp lý sản phẩm
**Nhóm sản phẩm đặc biệt:** có / không — [nhóm nào]
**Giấy phép, công bố, chứng nhận:**
**Được nói:**
**Không được nói:**

## Bằng chứng
**Số liệu:**
**Khách hàng tiêu biểu:**
**Lời khách hàng:**
> "[trích]" — [ai]
**Chủ đề giá trị:**
| Chủ đề | Bằng chứng |
|---|---|
| | |

## Mục tiêu
**Mục tiêu kinh doanh:**
**Hành động chuyển đổi:**
**Số liệu hiện tại:**

## Quảng cáo trả phí (tùy chọn)
**CPA / ROAS mục tiêu:**
**Mức sàn:**
**Ngân sách tháng, dao động ngày:**
**Chuyển đổi được tính:**
| Hành động | Nghĩa là | Giá trị | Dùng cho tối ưu giá thầu? |
|---|---|---|---|
| | | | |
**Điểm yếu đo lường đã biết:**
**Lead tốt vs. điền form:**
**Chiến dịch:** [tên] — [mục đích]
**Claude được:** đọc, so sánh, cảnh báo, soạn nháp, đề xuất
**Claude không được (khi chưa duyệt):** đổi ngân sách/giá thầu, tắt/bật, sửa đo lường, đăng quảng cáo

## Bài học
*Quyết định và bài học đã kiểm chứng. Mới nhất ở trên. Giữ khoảng 20 dòng đang hiệu lực.*
| Ngày | Bài học | Bằng chứng | Áp dụng cho | Trạng thái |
|---|---|---|---|---|
| | | | | |

## Nhật ký thay đổi
*Mới nhất ở trên. Mỗi lần sửa một dòng: đổi gì và vì sao.*
- v1 ([ngày]) — Tạo hồ sơ.
```

---

## Bước 4: Xác nhận, đánh phiên bản và lưu

- Cho người dùng xem hồ sơ hoàn chỉnh và hỏi có cần chỉnh gì không.
- **Đánh phiên bản và ghi nhật ký** — đây là dấu vết của một tài liệu mà mọi skill khác đọc:
  - **Hồ sơ mới:** `Phiên bản: v1` và một dòng nhật ký `- v1 ([hôm nay]) — Tạo hồ sơ.`
  - **Cập nhật:** tăng phiên bản (v2 → v3…), sửa ngày cập nhật, **thêm dòng nhật ký mới lên đầu** tóm tắt đổi gì và vì sao. Không sửa hay đảo thứ tự các dòng cũ.
  - Dòng tốt nêu mục bị sửa và lý do, ví dụ:
    - `- v3 (2026-07-16) — Định vị lại từ "phần mềm bán hàng" thành "quản lý chuỗi cửa hàng"; thêm chủ chuỗi F&B vào tệp khách.`
    - `- v2 (2026-06-02) — Viết lại giá trị cốt lõi và lời từ chối sau 5 cuộc phỏng vấn khách; thêm đối thủ ABC.`
  - Ngày theo dạng YYYY-MM-DD.
  - **Chỉ sửa lỗi chính tả:** không tăng phiên bản, không thêm nhật ký. Mọi thay đổi khác đều tăng phiên bản. Nếu là định vị lại thật sự, nói rõ — các skill khác sẽ làm việc theo định vị mới.
- **Lưu:**
  - Có thư mục dự án: lưu vào `.agents/product-marketing.md`. Nói với người dùng: "Các skill marketing khác sẽ tự dùng hồ sơ này. Nhật ký ở cuối ghi lại mọi lần sửa."
  - Trên app Claude: đưa toàn văn hồ sơ trong **một** khối để sao chép (hoặc lưu thành tài liệu nếu có công cụ), rồi hướng dẫn: "Lưu hồ sơ này vào kiến thức (knowledge) của Project bạn dùng cho marketing. Từ nay mọi cuộc trò chuyện trong Project đó sẽ dùng hồ sơ. Khi cần sửa, gọi lại skill này và dán hồ sơ hiện tại."

---

## Ghi bài học

Nhật ký thay đổi ghi hồ sơ đã đổi thế nào. **Bài học** ghi những gì đội ngũ học được khi làm thật: góc nào thắng, ưu đãi nào thất bại, quyết định nào đã chốt và vì sao. Các skill viết nội dung (copywriting, emails, ads, ad-creative, social, livestream, chat-selling) đọc mục này trước khi viết, để bản nháp sau bắt đầu từ những gì đã biết.

**Mỗi bài học một dòng:**
- **Bài học:** một câu, đủ cụ thể để làm thay đổi bản nháp. "Tiêu đề nêu giá thắng tiêu đề nêu kết quả trên trang bảng giá" là được. "Viết rõ hơn" thì không.
- **Bằng chứng:** thử nghiệm, chiến dịch hoặc nguồn, kèm con số và cỡ mẫu. "Phương án B +18% đơn, 2.400 lượt truy cập mỗi nhánh, 3 tuần."
- **Áp dụng cho:** kênh, nhóm khách hoặc skill bị ảnh hưởng.
- **Trạng thái:** `đang áp dụng`, `theo dõi` (mới một lần, nên thử lại) hoặc `ngừng`.

**Đáng ghi:**
- Kết quả thử nghiệm đạt đủ cỡ mẫu dự kiến, hoặc cùng một xu hướng thấy ở từ hai chiến dịch trở lên
- Quyết định của người dùng kèm lý do (định vị, giá, cắt kênh) mà bản nháp sau phải tôn trọng
- Điều người dùng sửa từ hai lần trở lên ("đừng bao giờ gọi là nền tảng")

**Không ghi:** chuyện một lần (ghi `theo dõi` hoặc bỏ), ghi chú công việc, và những thứ thuộc mục khác (lời từ chối mới → mục Lời từ chối; câu nói mới của khách → mục Ngôn ngữ khách hàng).

**Khi nào ngừng một bài học:** thử nghiệm sau cho kết quả ngược lại, sản phẩm hoặc thị trường đã đổi (giá mới, tệp khách mới), hoặc hai quý không còn liên quan. Đổi trạng thái thành `ngừng` kèm một dòng lý do thay vì xóa, để không ai thử lại câu hỏi đã có lời giải. Đưa dòng đã ngừng xuống cuối, lưu trữ khi bảng vượt khoảng 20 dòng đang áp dụng.

**Ai ghi:** skill nào hoàn thành một thử nghiệm, chiến dịch hoặc buổi rút kinh nghiệm đều có thể đề xuất một dòng. Cho người dùng xem dòng đề xuất, thêm khi được đồng ý, kèm tăng phiên bản và dòng nhật ký như mọi thay đổi khác. Các vòng việc chạy định kỳ làm việc này ở bước kết thúc phiên (xem `marketing-loops`).

---

## Mẹo

- **Hỏi cụ thể:** "Điều gì làm khách bực nhất khiến họ tìm đến bạn?" thay vì "Sản phẩm giải quyết vấn đề gì?"
- **Ghi đúng lời khách:** lời khách nói thật hơn câu chữ trau chuốt. Nguồn tốt: inbox, đánh giá trên sàn, bình luận, ghi âm cuộc gọi tư vấn.
- **Xin ví dụ:** "Anh/chị kể một trường hợp cụ thể được không?" mở ra câu trả lời tốt hơn.
- **Xác nhận dần:** tóm tắt từng mục và xác nhận trước khi sang mục sau.
- **Bỏ qua mục không áp dụng:** không phải sản phẩm nào cũng cần đủ mục (ví dụ Vai trò mua với B2C đơn giản, Quảng cáo nếu không chạy quảng cáo).
