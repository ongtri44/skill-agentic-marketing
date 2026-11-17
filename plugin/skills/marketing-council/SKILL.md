---
name: marketing-council
description: "Muốn nghe nhiều góc nhìn chuyên gia về một quyết định marketing, hoặc hỏi một marketer nổi tiếng sẽ nói gì: hội đồng cố vấn mô phỏng (Seth Godin, David Ogilvy, April Dunford, Byron Sharp, Alex Hormozi và người khác), mỗi người dựa trên khung lý thuyết đã công bố, chỉ ra chỗ bất đồng và đưa khuyến nghị phù hợp thị trường Việt Nam. Thực thi thì chuyển sang skill tương ứng."
metadata:
  version: 1.0.0
  upstream: marketing-council 1.0.3
---

# Hội đồng cố vấn marketing

Bạn triệu tập một **hội đồng cố vấn mô phỏng**: các marketer huyền thoại có khung lý thuyết, quan điểm đã công bố và nguyên tắc quen thuộc được áp vào vấn đề cụ thể của người dùng. Giá trị không nằm ở một ý kiến đơn lẻ mà ở **sự bất đồng** — các lăng kính va chạm có ích, để người dùng thấy đánh đổi thật trước khi chọn hướng.

**Đây là mô phỏng, không phải người thật.** Mọi ý kiến phải dựa trên điều cố vấn thực sự viết hoặc nói (xem Luật căn cứ). Ghi rõ đầu ra là mô phỏng.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Rồi làm rõ (chỉ hỏi phần thiếu):
1. **Câu hỏi** — quyết định hay sản phẩm công việc nào được xem xét (chiến lược, trang đích, đổi giá, kế hoạch ra mắt, đổi thương hiệu, tài khoản quảng cáo, kịch bản livestream)?
2. **Mức độ quan trọng** — tốt thì sao, xấu thì sao; đã thử gì?
3. **Chế độ** — ý kiến nhanh, phiên hội đồng, hay toàn hội đồng. Mặc định: phiên hội đồng.

## Chế độ

| Chế độ | Số ghế | Khi nào |
|---|---|---|
| **Ý kiến nhanh** | 1 | "Ogilvy sẽ nói gì về tiêu đề này?" |
| **Phiên hội đồng** (mặc định) | 3–5 | Quyết định thật cần lăng kính đối lập |
| **Toàn hội đồng** | Cả 12 | Quyết định chiến lược lớn — đầu ra dài; chỉ đề xuất khi đáng |

## Hội đồng

Mười hai cố vấn, chọn để lăng kính va nhau. Hồ sơ đầy đủ trong `references/advisors/` (tiếng Anh) — chỉ mở hồ sơ của người được mời ngồi.

| Cố vấn | Lăng kính | Hồ sơ |
|---|---|---|
| **Seth Godin** | Đáng chú ý, marketing được cho phép, khán giả nhỏ nhất khả thi | [seth-godin.md](references/advisors/seth-godin.md) |
| **David Ogilvy** | Quảng cáo thương hiệu dựa nghiên cứu, kỷ luật phản hồi trực tiếp | [david-ogilvy.md](references/advisors/david-ogilvy.md) |
| **Eugene Schwartz** | Dẫn dòng khao khát sẵn có; các mức nhận biết và độ tinh của thị trường | [eugene-schwartz.md](references/advisors/eugene-schwartz.md) |
| **Claude Hopkins** | Quảng cáo khoa học — thử mọi thứ, nội dung có lý do | [claude-hopkins.md](references/advisors/claude-hopkins.md) |
| **Gary Halbert** | Đám đông đói — thị trường và danh sách trước sản phẩm và chữ | [gary-halbert.md](references/advisors/gary-halbert.md) |
| **Russell Brunson** | Phễu, thang giá trị, móc–chuyện–ưu đãi | [russell-brunson.md](references/advisors/russell-brunson.md) |
| **Alex Hormozi** | Xây ưu đãi và phương trình giá trị; khối lượng và đòn bẩy | [alex-hormozi.md](references/advisors/alex-hormozi.md) |
| **April Dunford** | Định vị so với lựa chọn thay thế thật | [april-dunford.md](references/advisors/april-dunford.md) |
| **Rory Sutherland** | Khoa học hành vi, "tâm-lý-logic"; điều ngược với ý hay cũng có thể là ý hay | [rory-sutherland.md](references/advisors/rory-sutherland.md) |
| **Byron Sharp** | Khoa học thương hiệu dựa bằng chứng — hiện diện trong tâm trí và trên kệ, độ phủ hơn lòng trung thành | [byron-sharp.md](references/advisors/byron-sharp.md) |
| **Ann Handley** | Nghề viết và nội dung; marketing chậm hơn, can đảm hơn | [ann-handley.md](references/advisors/ann-handley.md) |
| **Gary Vaynerchuk** | Chênh lệch giá chú ý — bản địa trên kênh đang rẻ, với khối lượng lớn | [gary-vaynerchuk.md](references/advisors/gary-vaynerchuk.md) |

## Xếp ghế

Phiên hội đồng 3–5 người: (1) 2–3 người có lăng kính khớp loại câu hỏi; (2) **luôn có ít nhất một người phản biện** — quan điểm đã công bố trái với hướng câu hỏi đang nghiêng; (3) tôn trọng yêu cầu cụ thể ("tôi muốn Hormozi và Godin").

| Loại câu hỏi | Hợp | Phản biện tự nhiên |
|---|---|---|
| Định vị/thông điệp | Dunford, Godin, Schwartz | Sharp (hoài nghi khác biệt hóa) |
| Ưu đãi/giá | Hormozi, Halbert, Brunson | Sutherland (giá ≠ logic giá trị), Godin (cảnh báo đua xuống đáy) |
| Xây thương hiệu | Sharp, Ogilvy, Sutherland | Hopkins, Halbert (cho xem doanh số) |
| Duyệt nội dung/sáng tạo | Ogilvy, Schwartz, Halbert, Handley | Sutherland (thử cái phi lý) |
| Phễu/đường chuyển đổi | Brunson, Hormozi, Hopkins | Godin (cho phép hơn ép buộc), Handley (đang bào mòn niềm tin) |
| Chiến lược nội dung | Handley, Godin, Vaynerchuk | Sharp (độ phủ thắng chiều sâu), Hopkins (phản hồi đâu?) |
| Quảng cáo/truyền thông | Hopkins, Sharp, Vaynerchuk | Godin (gián đoạn là một loại thuế) |
| Tăng trưởng/mở rộng | Hormozi, Vaynerchuk, Sharp | Handley (xói chất lượng), Dunford (mở rộng một định vị mơ hồ) |
| Chọn khán giả/kênh | Vaynerchuk, Sharp, Halbert | Godin (khán giả nhỏ nhất khả thi vs độ phủ đại trà) |
| Chiến lược ra mắt | Brunson, Godin, Halbert | Sharp (ra mắt phai nhanh; hiện diện mới cộng dồn) |

## Quy trình phiên

1. **Mở hồ sơ** của người được mời.
2. **Nghiên cứu trực tiếp (tùy chọn)** — khi câu hỏi đủ cụ thể mà hồ sơ có thể không phủ, hoặc người dùng muốn trích nguồn.
3. **Ý kiến từng cố vấn** — 2–4 đoạn: mở bằng các *câu hỏi đặc trưng* của họ áp vào trường hợp; áp khung lý thuyết vào chi tiết cụ thể (không phải lời khuyên chung gắn tên); khuyến nghị với mức tin chắc họ thật sự có; giọng theo ghi chú trong hồ sơ, không bịa trích dẫn.
4. **Bản đồ bất đồng** — phần giá trị nhất. 2–4 xung đột thật, gọi tên đánh đổi bên dưới mỗi xung đột (ví dụ "Sharp vs Godin thực chất là độ phủ vs độ cộng hưởng — ràng buộc nào chặt hơn với *doanh nghiệp này*?"), và bằng chứng nào sẽ phân xử.
5. **Tổng hợp của chủ tọa** — khuyến nghị hợp nhất với giai đoạn, ngành, ràng buộc của người dùng; cảnh báo của cố vấn nào cần giữ làm "dây báo động"; bước tiếp theo cụ thể kèm skill thực thi.

**Áp vào thị trường Việt Nam:** các cố vấn chủ yếu viết cho thị trường Mỹ/Anh. Khi bối cảnh khác (bán qua Zalo/Messenger, sàn TMĐT, livestream, COD, quy định cấm quảng cáo so sánh trực tiếp, văn hóa quan hệ trong B2B), nói rõ trong ý kiến và **suy luận bằng phép tương tự có ghi rõ**: "Hopkins chưa từng thấy livestream, nhưng nguyên tắc dùng mẫu thử của ông ánh xạ thế này…". Lời khuyên vi phạm pháp luật Việt Nam (ví dụ so sánh gọi tên đối thủ trong quảng cáo, khan hiếm giả) phải được chủ tọa chỉ ra và điều chỉnh ([vn-legal.md](references/vn/vn-legal.md)).

## Nghiên cứu trực tiếp

Khi chủ đề cụ thể (ngách, thay đổi kênh, thay đổi nền tảng hiện tại) hoặc người dùng muốn nguồn: dùng skill nghiên cứu sâu nếu có; nếu không, tìm web `[tên cố vấn] + [chủ đề]` cho từng người, ưu tiên nguồn gốc (sách, blog, bản tin, bài nói của chính họ) hơn bài tổng hợp. Đưa phát hiện vào ý kiến kèm trích nguồn ("Trong một cuộc phỏng vấn năm 2023 trên X, Dunford lập luận…"). Nghiên cứu mâu thuẫn hồ sơ → tin nghiên cứu và ghi chú việc sửa.

## Luật căn cứ (không thương lượng)

- **Ghi là mô phỏng** một lần ở đầu.
- **Không bịa trích dẫn.** Chỉ trích nguyên văn câu kiểm chứng được trong hồ sơ hoặc nghiên cứu, kèm nguồn; còn lại thì diễn đạt lại: "Quan điểm của Hopkins trong *Scientific Advertising* là…". Trích dẫn tiếng Anh có thể dịch, ghi rõ là bản dịch.
- **Không bịa ủng hộ hay lên án.** Chỉ mô phỏng cố vấn *áp khung* vào sản phẩm; không bao giờ nói hay ngụ ý người thật có ý kiến về công ty cụ thể của người dùng.
- **Cẩn trọng hơn với người còn sống** (Godin, Brunson, Hormozi, Dunford, Sutherland, Sharp, Handley, Vaynerchuk) — quan điểm thay đổi; ưu tiên nghiên cứu với điều nhạy thời gian; không mô phỏng họ bình luận về đối thủ có tên hay tranh cãi.
- **Bất đồng về thực chất, không phải biếm họa** — mỗi ý kiến là phiên bản mạnh nhất của quan điểm đó.
- **Hồ sơ không giao với câu hỏi** → nói vậy và suy luận bằng phép tương tự có ghi rõ.

## Định dạng đầu ra

```
> Hội đồng mô phỏng — mỗi ý kiến được xây từ khung lý thuyết và quan điểm
> đã công bố của cố vấn, không phải đánh giá thật của họ.

## Câu hỏi trước hội đồng
[1–2 câu + điều đang được đặt cược]

## Ngồi ghế: [A], [B], [C] ([chế độ])
[Một dòng vì sao chọn, ai là người phản biện]

### [A] — [lăng kính, 3–5 từ]
[2–4 đoạn]
**Kết luận:** [một câu]

### [B] — …

## Hội đồng bất đồng ở đâu
1. **[Xung đột]** — [A] nói X vì [khung]; [B] nói Y vì [khung].
   Đánh đổi thật: [...]. Điều sẽ phân xử: [bằng chứng/thử nghiệm].

## Tổng hợp của chủ tọa
[Khuyến nghị hợp giai đoạn và ràng buộc, đã điều chỉnh cho thị trường/pháp lý Việt Nam]
- **Làm:** [2–4 bước cụ thể]
- **Dây báo động:** [cảnh báo của ai cần theo dõi, tín hiệu nào]
- **Thực thi bằng:** [skill]
```

## Thêm cố vấn riêng

Người dùng có thể thêm cố vấn ("thêm cố vấn của tôi"). Tạo hồ sơ theo [references/advisor-template.md](references/advisor-template.md) — cùng các trường (lăng kính, khung, quan điểm đã công bố kèm nguồn, câu hỏi đặc trưng, hợp nhất/điểm mù, ghi chú giọng, tác phẩm chính). Với người không nổi tiếng (sếp cũ, lãnh đạo nội bộ, chuyên gia trong nước), người dùng phải cung cấp quan điểm — không bịa. Lưu ở `.agents/advisors/<ten>.md` trong dự án (hoặc kiến thức Project trên app Claude) để giữ lâu và không đụng bản cập nhật.

## Phản mẫu

- **Hội đồng đồng thuận** — năm ý kiến cùng chúc phúc kế hoạch sẵn có. Xếp lại ghế với người phản biện thật.
- **Lời khuyên chung gắn tên** — ý kiến vẫn đúng khi đổi tên người thì không phải ý kiến.
- **Súp trích dẫn** — khâu các câu nói nổi tiếng thay vì áp phương pháp phía sau.
- **Dùng hội đồng để làm việc thực thi** — hội đồng quyết hướng, không viết trang đích. Chuyển sang skill thực thi khi đã có hướng.
- **Mười hai cố vấn cho một tiêu đề** — số ghế tương xứng mức quan trọng.

## Skill liên quan

- `product-marketing` — khi ý kiến của Dunford thắng, làm định vị
- `offers`, `pricing` — khi hướng Hormozi/Halbert thắng
- `copywriting`, `copy-editing` — sửa nội dung đã được duyệt
- `ads`, `ad-creative` — chiến lược truyền thông/sáng tạo
- `content-strategy`, `social` — khi hướng Handley/Vaynerchuk thắng
- `marketing-psychology` — cơ chế hành vi của Sutherland, hiện diện của Sharp
- `ab-testing` — khi bản đồ bất đồng nói "thử đi" (Hopkins sẽ đòi)
