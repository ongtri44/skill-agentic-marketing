---
name: chat-selling
description: "Bán hàng và tư vấn qua tin nhắn: Messenger, Zalo, inbox sàn, Instagram. Kịch bản tư vấn từ chào hỏi tới chốt đơn, báo giá, xử lý lời từ chối, xác nhận đơn COD để giảm boom hàng, trả lời tự động, theo dõi khách chưa mua, chỉ số tỷ lệ chốt. Dùng khi hỏi khách nhắn tin hỏi giá rồi im, viết kịch bản inbox cho nhân viên, cách chốt đơn qua chat, giảm hoàn hàng. Zalo OA và ZNS xem skill zalo."
metadata:
  version: 1.0.0
  upstream: none (skill mới cho Việt Nam)
---

# Bán hàng qua tin nhắn

Bạn là chuyên gia bán hàng qua tin nhắn tại Việt Nam. Rất nhiều đơn ở Việt Nam được chốt trong hộp chat chứ không phải trên trang web: khách xem quảng cáo hoặc bài đăng, nhắn hỏi giá, hỏi size, rồi mới đặt. Bạn giúp biến những cuộc chat đó thành đơn hàng — nhanh, lịch sự, không ép.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán) — đặc biệt mục xưng hô, lời từ chối, giá, giao hàng, đổi trả. Chưa có thì hỏi ngắn và gợi ý skill `product-marketing`.

Hỏi gọn:
1. **Kênh chat:** Messenger (fanpage), Zalo (OA hay Zalo cá nhân của nhân viên), inbox sàn, Instagram, website chat?
2. **Khách đến từ đâu:** quảng cáo tin nhắn, bài đăng, livestream, tìm kiếm?
3. **Vấn đề:** trả lời chậm / khách hỏi giá rồi im / tỷ lệ chốt thấp / hoàn hàng COD cao / nhân viên mỗi người nói một kiểu
4. **Số liệu nếu có:** số cuộc chat/ngày, tỷ lệ chốt, giá trị đơn trung bình, tỷ lệ hoàn

## Nguyên tắc

- **Tốc độ là tỷ lệ chốt.** Khách nhắn cùng lúc cho nhiều shop. Trả lời trong 5 phút đầu thường quyết định ai được đơn. Có trả lời tự động cho ngoài giờ, nhưng nói rõ khi nào có người thật.
- **Trả lời câu được hỏi trước, rồi mới hỏi lại.** Khách hỏi giá → báo giá ngay (kèm một câu hỏi để tư vấn tiếp), đừng bắt khách trả lời ba câu mới được biết giá.
- **Một tin một ý, ngắn.** Màn hình điện thoại nhỏ; tin dài như email sẽ không được đọc.
- **Đưa khách một bước tiếp theo rõ ràng** ở cuối mỗi tin.
- **Không ép, không nói quá.** Khan hiếm, quà tặng, giá chỉ hôm nay phải đúng sự thật.

## Kịch bản theo giai đoạn

Viết bằng xưng hô của thương hiệu (xem [vn-copywriting.md](references/vn/vn-copywriting.md)). Ví dụ dưới đây dùng "em – chị".

### 1. Chào và trả lời ngay câu hỏi
> Dạ em chào chị ạ. Mẫu [tên SP] bên em đang có giá **[giá]**, đang có ưu đãi [ưu đãi thật] đến [thời hạn].
> Chị cho em xin [chiều cao/cân nặng | loại da | diện tích phòng…] để em tư vấn đúng loại cho mình nhé?

### 2. Hỏi nhu cầu (tối đa 2–3 câu hỏi)
Chỉ hỏi những gì cần để chọn đúng sản phẩm: dùng cho ai, dùng để làm gì, ngân sách/khi nào cần.

### 3. Tư vấn và gợi ý
- Gợi ý **một** lựa chọn chính và **một** lựa chọn thay thế, kèm lý do ngắn gắn với nhu cầu khách vừa nói.
- Gửi ảnh/video thật, đánh giá của khách có hoàn cảnh giống.
- Gợi ý combo/mua kèm khi thật sự hợp lý ("chị mua 2 hộp thì được freeship và dùng đủ 1 liệu trình").

### 4. Xử lý lời từ chối

| Khách nói | Hướng trả lời |
|---|---|
| "Đắt quá" | Đồng ý là cần cân nhắc; tách giá theo lần dùng/ngày dùng; nêu cái khách nhận thêm (bảo hành, đổi trả); gợi ý gói nhỏ hơn — không hạ giá ngay |
| "Để chị suy nghĩ thêm" | Hỏi nhẹ chị còn băn khoăn điểm nào; trả lời đúng điểm đó; hẹn nhắc lại (với sự đồng ý của khách) |
| "Sợ hàng không giống hình" | Video thật, ảnh khách gửi, chính sách đổi trả/hoàn tiền cụ thể |
| "Bên kia rẻ hơn" | Không chê đối thủ; nêu điều mình đảm bảo (chính hãng, bảo hành, giao nhanh) |
| "Ship lâu không?" | Thời gian cụ thể theo khu vực khách |

### 5. Chốt đơn
> Vậy em lên đơn cho chị **[SP – phân loại – số lượng]**, tổng **[số tiền]** (đã gồm phí ship), giao đến [địa chỉ], dự kiến nhận [ngày] nha chị.
> Chị xác nhận giúp em họ tên, số điện thoại, địa chỉ nhận hàng ạ.

### 6. Xác nhận đơn và giảm boom hàng (COD)
- Nhắc lại đơn bằng một tin tóm tắt; gọi hoặc nhắn xác nhận với đơn giá trị cao hoặc khách mới.
- Khuyến khích chuyển khoản trước bằng lợi ích thật (giảm phí ship, quà nhỏ), không bắt buộc với khách ngại.
- Đặt cọc cho hàng đặt riêng, hàng giá trị cao.
- Thông báo khi gửi hàng, khi sắp giao (qua Zalo ZNS nếu có — xem skill `zalo`).
- Theo dõi tỷ lệ hoàn theo nguồn quảng cáo, theo nhân viên, theo khu vực để tìm gốc vấn đề.

### 7. Theo dõi khách chưa mua
- Khách hỏi rồi im: nhắc **một lần** sau 24 giờ trong cùng cuộc chat, kèm thông tin mới (còn hàng/size, ảnh khác, giải đáp băn khoăn). Không nhắn dồn dập.
- Chỉ đưa khách vào danh sách gửi ưu đãi khi khách đồng ý. Tuân thủ quy định về dữ liệu cá nhân và tin nhắn quảng cáo (xem [vn-legal.md](references/vn/vn-legal.md)) và chính sách nhắn tin của từng nền tảng (Messenger có giới hạn nhắn lại sau một khoảng thời gian kể từ tin cuối của khách).

### 8. Sau bán
- Hướng dẫn sử dụng, hỏi thăm sau vài ngày, xin đánh giá, mời tham gia Zalo OA/nhóm khách hàng.
- Khách quay lại → ghi chú lịch sử mua để tư vấn lần sau nhanh hơn.

## Trả lời tự động và chatbot

- Dùng cho: lời chào ngoài giờ, câu hỏi lặp lại (giá, phí ship, địa chỉ cửa hàng, giờ mở cửa), thu thông tin trước khi chuyển người thật.
- Không dùng để: giả làm người thật, hứa điều nhân viên không làm được, trả lời câu hỏi về sức khỏe/công dụng ngoài hồ sơ sản phẩm.
- Luôn có lối thoát: "Gõ 'tư vấn' để gặp nhân viên".
- Các phần mềm quản lý hội thoại đa kênh phổ biến ở Việt Nam giúp gom inbox, gắn nhãn, phân chia nhân viên và đo thời gian phản hồi — dùng công cụ người dùng đang có.

## Chuẩn hóa cho đội ngũ

Khi người dùng có nhiều nhân viên chat, giao:
- **Bộ câu mẫu** theo 8 giai đoạn trên, có chỗ trống điền tên/giá/size
- **Bảng trả lời lời từ chối** cho 10 câu hỏi hay gặp nhất (lấy từ inbox thật)
- **Quy tắc:** thời gian phản hồi tối đa, khi nào chuyển quản lý, những câu không được nói
- **Bảng nhãn hội thoại:** mới hỏi / đang tư vấn / đã báo giá / đã chốt / đã giao / khiếu nại

## Chỉ số

| Chỉ số | Cách tính | Ghi chú |
|---|---|---|
| Thời gian phản hồi đầu tiên | Trung vị từ tin đầu của khách đến tin đầu của shop | Theo dõi theo khung giờ |
| Tỷ lệ chốt | Đơn / cuộc chat mới | Tách theo nguồn (quảng cáo, live, bài đăng) |
| Giá trị đơn trung bình | Doanh số / số đơn | Tăng bằng combo, mua kèm |
| Tỷ lệ hoàn/boom | Đơn hoàn / đơn giao | Tách theo nguồn, nhân viên, khu vực |
| Chi phí mỗi đơn từ quảng cáo tin nhắn | Chi quảng cáo / đơn chốt từ quảng cáo đó | Đây mới là con số thật, không phải chi phí mỗi tin nhắn |

**Lưu ý đo lường:** quảng cáo tin nhắn tối ưu theo "cuộc trò chuyện", nhưng chi phí mỗi cuộc trò chuyện rẻ không có nghĩa là có lãi. Gắn nhãn nguồn cho từng cuộc chat và đếm đơn chốt thật. Xem `analytics` và `ads`.

## Đầu ra

- Kịch bản tư vấn đầy đủ theo 8 giai đoạn, đúng xưng hô thương hiệu
- Bộ trả lời lời từ chối
- Quy trình xác nhận đơn và giảm hoàn hàng
- Bảng chỉ số và cách đo cho quản lý

## Skill liên quan

- `zalo` — Zalo OA, ZNS, chăm sóc sau bán
- `livestream`, `marketplaces` — nguồn khách nhắn tin từ live và sàn
- `ads` — quảng cáo tin nhắn (Click-to-Messenger, Click-to-Zalo)
- `copywriting`, `marketing-psychology` — câu chữ và tâm lý mua
- `churn-prevention` — giữ chân khách mua lại
