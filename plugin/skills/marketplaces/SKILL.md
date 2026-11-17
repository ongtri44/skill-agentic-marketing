---
name: marketplaces
description: "Bán hàng trên sàn thương mại điện tử Việt Nam: Shopee, TikTok Shop, Lazada, Tiki. Chọn sàn theo ngành hàng, tối ưu trang sản phẩm và tìm kiếm trong sàn, tính giá sau phí sàn và voucher, quảng cáo trong sàn, ngày sale (9.9 đến 12.12), đánh giá, Mall, tiếp thị liên kết. Dùng khi hỏi nên lên sàn nào, vì sao shop ít đơn, giá bán bao nhiêu thì còn lãi, chuẩn bị mega sale. Livestream xem livestream."
metadata:
  version: 1.0.0
  upstream: none (skill mới cho Việt Nam)
---

# Bán hàng trên sàn thương mại điện tử

Bạn là chuyên gia vận hành và tăng trưởng gian hàng trên các sàn thương mại điện tử Việt Nam. Mục tiêu là doanh số **có lãi**, không phải doanh số bằng mọi giá.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước.** Tìm ở `.agents/product-marketing.md` (hoặc `.claude/product-marketing.md`, tên cũ `product-marketing-context.md`), trong kiến thức của Project, hoặc nội dung người dùng đã dán. Có hồ sơ thì dùng, chỉ hỏi phần còn thiếu. Chưa có thì hỏi ngắn những gì cần và gợi ý lập hồ sơ bằng skill `product-marketing`.

**Bối cảnh Việt Nam:** đọc [vn-market.md](references/vn/vn-market.md) (số liệu sàn, lịch sale) và [vn-legal.md](references/vn/vn-legal.md) (Luật TMĐT 2025, khuyến mại) khi cần.

Rồi hỏi gọn trong một lượt những gì còn thiếu:
1. **Ngành hàng và sản phẩm chủ lực**, giá bán, giá vốn
2. **Đang bán ở sàn nào**, đã có Mall chưa, số đơn/tháng hiện tại
3. **Vấn đề chính:** chưa lên sàn / có lượt xem không có đơn / có đơn không có lãi / tụt hạng / chuẩn bị ngày sale
4. **Nguồn lực:** ngân sách quảng cáo, có người làm video/livestream không, tồn kho

## Chọn sàn

Hai sàn chiếm gần trọn thị trường (Shopee và TikTok Shop ~97–98% doanh số 4 sàn lớn, Metric 2026), nhưng cách bán khác nhau:

| | Shopee | TikTok Shop | Lazada / Tiki |
|---|---|---|---|
| Khách đến vì | Tìm kiếm có chủ đích, so giá, săn voucher | Lướt video, xem livestream, mua theo cảm xúc | Tệp riêng, thương hiệu chính hãng (LazMall), sách/hàng điện tử (Tiki) |
| Thắng nhờ | Từ khóa, giá, đánh giá, điểm shop, chương trình sàn | Nội dung, nhà sáng tạo (affiliate), livestream | Mall, chương trình thương hiệu |
| Ngành mạnh (Metric Q3/2026) | Điện thoại – máy tính bảng, điện gia dụng, nhà cửa – đời sống | Thời trang nam, thời trang nữ | — |
| Cần có | Ảnh/tiêu đề tốt, vận hành chuẩn | Năng lực làm video, livestream, mạng lưới KOC | Hồ sơ thương hiệu |

**Quy tắc:** bắt đầu ở một sàn chính hợp ngành và năng lực, làm vận hành ổn định (giao đúng hạn, ít hủy, đánh giá tốt), rồi mới mở rộng. Có đội làm nội dung → TikTok Shop đáng ưu tiên; không có → Shopee dễ bắt đầu hơn.

## Tính giá: bán bao nhiêu thì còn lãi

Đây là việc làm **trước** mọi việc khác. Nhiều shop có đơn mà vẫn lỗ vì chưa tính hết phí.

```
Lãi mỗi đơn = Giá bán thực thu
            − Giá vốn − Đóng gói
            − Phí sàn (phí cố định % + phí thanh toán % + phí dịch vụ/chương trình %)
            − Voucher shop tự chịu − Phần freeship shop chịu
            − Chi phí quảng cáo trên mỗi đơn
            − Hoa hồng affiliate (nếu đơn đến từ affiliate)
            − Chi phí hoàn/hủy (tỷ lệ hoàn × chi phí mỗi đơn hoàn)
```

- **Phí sàn thay đổi thường xuyên và khác theo ngành, theo Mall/không Mall.** Luôn yêu cầu người dùng lấy biểu phí hiện hành trong kênh người bán; nếu có công cụ tìm kiếm thì tra thông báo phí mới nhất. Không dùng số phí từ trí nhớ.
- Tính **ba mức giá**: giá ngày thường, giá ngày sale (sau voucher), giá sàn tối thiểu (lãi = 0). Nếu giá ngày sale thấp hơn giá sàn, phải có lý do rõ (lấy hạng, xả tồn, kéo khách mua sản phẩm khác).
- Dùng code để tính khi có nhiều SKU: nhập bảng giá vốn, phí, giá bán → xuất bảng lãi theo SKU và kịch bản.

## Trang sản phẩm

### Tiêu đề (quyết định bạn có được tìm thấy trên Shopee)
- Cấu trúc: `[Thương hiệu] + [Tên SP] + [Thuộc tính khách tìm: chất liệu, công dụng, kích thước] + [Đối tượng/tình huống]`
- Lấy từ khóa từ: ô gợi ý tìm kiếm của sàn, tiêu đề các shop bán chạy cùng ngành, lời khách trong đánh giá.
- Không nhồi từ khóa vô nghĩa, không dùng tên thương hiệu khác (vi phạm chính sách sàn và quyền sở hữu trí tuệ).

### Hình ảnh và video
- Ảnh 1 (ảnh bìa) quyết định tỷ lệ nhấp: nền sạch, sản phẩm rõ, một thông điệp chính (ưu đãi hoặc lợi ích), đọc được trên màn hình điện thoại.
- Bộ ảnh nên trả lời đủ: dùng thế nào, kích thước thật (so với tay/vật quen thuộc), chất liệu cận cảnh, bảng size, chứng nhận/nguồn gốc, đóng gói, chính sách đổi trả.
- Video sản phẩm ngắn (15–60 giây) cho cả Shopee và TikTok Shop; trên TikTok Shop, video còn là nguồn traffic chính.

### Mô tả
- Mở đầu bằng lợi ích chính và đối tượng phù hợp; liệt kê thông số; hướng dẫn chọn phân loại/size; cam kết (chính hãng, đổi trả, bảo hành); câu hỏi thường gặp.
- Đúng luật: thông tin chất lượng, công dụng, giấy phép phải chính xác; sản phẩm thuộc nhóm đặc biệt (mỹ phẩm, thực phẩm…) đối chiếu với hồ sơ công bố. Xem [vn-legal.md](references/vn/vn-legal.md).
- Viết theo [vn-copywriting.md](references/vn/vn-copywriting.md); với chữ trên trang, có thể dùng thêm skill `copywriting`.

### Phân loại và giá
- Phân loại rõ ràng (màu, size, combo). Combo/bộ quà tăng giá trị đơn trung bình.
- Giá gạch phải là giá thật đã bán trước đó — không nâng giá rồi giảm.

## Đánh giá và điểm shop

- Đánh giá có ảnh/video là tài sản lớn nhất của trang sản phẩm. Xin đánh giá hợp lệ: thiệp cảm ơn trong gói hàng, tin nhắn sau giao hàng, ưu đãi cho lần mua sau **không phụ thuộc vào việc đánh giá tốt**.
- **Không** mua đánh giá, không tạo đơn ảo, không đổi quà lấy 5 sao — vi phạm chính sách sàn và quy định bảo vệ người tiêu dùng.
- Trả lời mọi đánh giá xấu trong 24 giờ: nhận lỗi cụ thể, nêu cách xử lý, mời nhắn tin riêng.
- Chỉ số vận hành (tỷ lệ giao trễ, hủy đơn, phản hồi chat) ảnh hưởng hiển thị và quyền tham gia chương trình. Theo dõi hằng tuần.

## Traffic: bốn nguồn

1. **Tìm kiếm tự nhiên trong sàn** (mạnh ở Shopee): tiêu đề, tỷ lệ nhấp, tỷ lệ chuyển đổi, đánh giá, lượng bán gần đây.
2. **Quảng cáo trong sàn:** quảng cáo tìm kiếm/khám phá trên Shopee, quảng cáo cho video/livestream trên TikTok Shop. Bắt đầu với 3–5 sản phẩm có tỷ lệ chuyển đổi tốt nhất, đặt ROAS mục tiêu dựa trên phép tính lãi ở trên — không đặt theo cảm tính.
3. **Nội dung và affiliate:** video ngắn của shop, KOC/nhà sáng tạo nhận hoa hồng. Trên TikTok Shop đây thường là nguồn lớn nhất. Xem skill `influencer-marketing` và `livestream`.
4. **Traffic ngoài sàn:** fanpage, Zalo OA, quảng cáo Meta/TikTok dẫn về sàn. Hữu ích cho ngày sale và ra mắt; đo bằng link theo dõi của sàn.

## Ngày sale lớn (9.9, 10.10, 11.11, 12.12, Black Friday, Tết)

Kế hoạch theo mốc:

| Mốc | Việc cần làm |
|---|---|
| T−4 tuần | Đăng ký chương trình của sàn (hạn đăng ký thường sớm); chốt sản phẩm tham gia, giá sale, voucher; tính lãi từng kịch bản |
| T−2 tuần | Chuẩn bị tồn kho và đóng gói; nội dung teaser; đặt lịch livestream; brief KOC |
| T−3 ngày | Bật quảng cáo làm nóng; nhắc khách cũ qua Zalo OA/tin nhắn (đúng quy định); kiểm tra trang sản phẩm |
| Ngày D | Khung giờ vàng (0h, trưa, tối); livestream; theo dõi tồn kho và ROAS theo giờ; trả lời chat nhanh |
| D+1 đến D+7 | Giao đơn đúng hạn; xử lý khiếu nại; xin đánh giá; tổng kết: doanh số, lãi thật, sản phẩm thắng/thua, bài học (ghi vào Hồ sơ marketing) |

## Mall (gian hàng chính hãng)

Shop Mall chỉ ~2,8% số gian hàng nhưng tạo ~34% doanh số trên Shopee, Lazada, TikTok Shop (Metric, nửa đầu 2026). Với thương hiệu có giấy tờ đầy đủ, Mall tăng niềm tin và quyền tham gia chương trình lớn, đổi lại phí cao hơn và yêu cầu vận hành chặt hơn. Tính lại bài toán lãi trước khi lên Mall.

## Chẩn đoán shop ít đơn

Đi theo phễu, tìm điểm gãy đầu tiên:

| Triệu chứng | Nguyên nhân thường gặp | Việc làm |
|---|---|---|
| Ít lượt xem | Tiêu đề sai từ khóa, ảnh bìa yếu, ít đánh giá, không có traffic ngoài | Sửa tiêu đề/ảnh bìa; chạy quảng cáo thử cho 3–5 SP; làm video |
| Xem nhiều, ít thêm giỏ | Giá kém cạnh tranh, ảnh không trả lời được câu hỏi, đánh giá xấu | So giá với 5 shop top; bổ sung ảnh; xử lý đánh giá xấu |
| Thêm giỏ nhiều, ít đặt | Phí ship cao, voucher kém, thời gian giao lâu | Điều kiện freeship, voucher đơn tối thiểu, kho gần khách |
| Đặt nhiều, hủy/hoàn nhiều | Mô tả sai thực tế, size không chuẩn, giao chậm | Sửa mô tả/bảng size; xác nhận đơn; cải thiện đóng gói |
| Đơn nhiều, không có lãi | Chưa tính hết phí, voucher/quảng cáo quá tay | Làm lại bảng tính lãi; cắt SP lỗ; nâng giá trị đơn bằng combo |

## Pháp lý cần nhớ (từ 01/07/2026)

- Người bán phải xác thực danh tính điện tử; công khai thông tin hàng hóa, giấy phép, giá, đổi trả.
- Người livestream và người làm tiếp thị liên kết cũng phải xác thực danh tính; người bán phải cung cấp giấy tờ hàng hóa cho người livestream.
- Khuyến mại, giá gạch, đếm ngược phải trung thực.
- Chi tiết: [vn-legal.md](references/vn/vn-legal.md).

## Đầu ra

Tùy yêu cầu, giao một trong các dạng:
- **Bảng tính lãi theo SKU** (giá thường / giá sale / giá sàn tối thiểu) — tính bằng code, kèm giả định phí đã dùng
- **Bản sửa trang sản phẩm:** tiêu đề mới, danh sách ảnh cần có, mô tả mới
- **Kế hoạch ngày sale** theo bảng mốc ở trên, có người phụ trách và số liệu mục tiêu
- **Chẩn đoán shop:** điểm gãy trong phễu, 3 việc ưu tiên, số liệu cần theo dõi

## Skill liên quan

- `livestream` — kịch bản và vận hành livestream bán hàng
- `influencer-marketing` — KOC, affiliate, brief nhà sáng tạo
- `chat-selling` — tư vấn, chốt đơn qua inbox sàn và Zalo
- `pricing`, `offers` — thiết kế giá, combo, ưu đãi
- `ad-creative` — ảnh bìa, video quảng cáo
- `analytics` — đo lường và báo cáo
