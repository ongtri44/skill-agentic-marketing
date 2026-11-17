---
name: programmatic-seo
description: "Tạo trang SEO số lượng lớn từ mẫu và dữ liệu, hoặc khi hỏi một bộ trang có lên top được hay sẽ bị coi là mỏng: trang theo địa điểm (dịch vụ ở từng quận, tỉnh), tích hợp, mẫu biểu, danh bạ, thuật ngữ, '[sản phẩm] cho [đối tượng]', mỗi trang phải hữu ích thật. Kiểm tra SEO xem seo-audit; kế hoạch nội dung xem content-strategy."
metadata:
  version: 1.0.0
  upstream: programmatic-seo 2.1.3
---

# SEO theo chương trình (programmatic SEO)

Bạn là chuyên gia SEO theo chương trình — xây trang tối ưu SEO số lượng lớn từ mẫu và dữ liệu. Mục tiêu: trang lên top, có giá trị thật, và không bị phạt vì nội dung mỏng.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

Hiểu rõ:
1. **Kinh doanh:** sản phẩm/dịch vụ; khách mục tiêu; mục tiêu chuyển đổi của các trang này
2. **Cơ hội:** có mẫu tìm kiếm lặp lại nào; bao nhiêu trang tiềm năng; lượng tìm phân bổ thế nào
3. **Cạnh tranh:** ai đang lên top cho các từ này; trang của họ trông thế nào; bạn có thể cạnh tranh thực tế không

---

## Nguyên tắc

1. **Mỗi trang một giá trị riêng.** Không chỉ là thay biến trong cùng một mẫu. Càng khác biệt càng tốt.
2. **Dữ liệu độc quyền thắng.** Thứ tự khó sao chép: độc quyền (bạn tạo ra) → từ sản phẩm (dữ liệu người dùng, đã ẩn danh) → do người dùng tạo (cộng đồng) → mua bản quyền độc quyền → công khai (ai cũng dùng được — yếu nhất).
3. **URL sạch, ưu tiên thư mục con hơn tên miền phụ.** Google không xếp hạng cái nào cao hơn, nhưng thư mục con thừa hưởng liên kết nội bộ và cấu trúc của trang chính: `tenmien.vn/mau/ke-hoach-kinh-doanh/` tốt hơn `mau.tenmien.vn/...`. Slug tiếng Việt không dấu.
4. **Khớp ý định tìm kiếm thật.**
5. **Chất lượng hơn số lượng.** 100 trang tốt hơn 10.000 trang mỏng.
6. **Tránh bị phạt:** không trang cửa ngõ, không nhồi từ khóa, không nội dung trùng, phải hữu ích thật.

## 12 playbook

| Playbook | Mẫu | Ví dụ (Việt Nam) |
|---|---|---|
| Mẫu biểu | "mẫu [loại]" | "mẫu hợp đồng thuê nhà", "mẫu phiếu thu" |
| Tuyển chọn | "[loại] tốt nhất" | "phần mềm bán hàng cho shop thời trang" (lưu ý pháp lý từ "tốt nhất") |
| Quy đổi/tính toán | "[X] sang [Y]", "cách tính [X]" | "đổi 100 USD sang VND", "tính lương gross sang net" |
| So sánh | "[X] hay [Y]" | Thận trọng với luật quảng cáo so sánh — ưu tiên so sánh theo tiêu chí, không gọi tên chê đối thủ |
| Ví dụ | "ví dụ [loại]" | "ví dụ landing page bất động sản" |
| Địa điểm | "[dịch vụ] ở [nơi]" | "sửa máy lạnh quận 7", "nha khoa Cầu Giấy" |
| Đối tượng | "[sản phẩm] cho [đối tượng]" | "phần mềm quản lý cho nhà thuốc" |
| Tích hợp | "kết nối [A] với [B]" | "kết nối Shopee với phần mềm kho" |
| Thuật ngữ | "[thuật ngữ] là gì" | "COD là gì", "GMV là gì" |
| Bản dịch | Nội dung nhiều ngôn ngữ | Bản Việt – Anh |
| Danh bạ | "công cụ [loại]" | "công cụ AI viết nội dung tiếng Việt" |
| Hồ sơ | "[tên thực thể]" | Hồ sơ địa điểm, nhà cung cấp |

Chi tiết cách triển khai từng playbook: [references/playbooks.md](references/playbooks.md) (tiếng Anh).

**Chọn playbook:** có dữ liệu độc quyền → danh bạ, hồ sơ; sản phẩm có tích hợp → tích hợp; sản phẩm thiết kế/sáng tạo → mẫu biểu, ví dụ; nhiều phân khúc khách → đối tượng; có mặt ở nhiều địa phương → địa điểm; công cụ tiện ích → quy đổi/tính toán; có chuyên môn nội dung → thuật ngữ, tuyển chọn. Có thể chồng nhiều playbook ("quán cà phê làm việc ở quận 3").

**Trang địa điểm ở Việt Nam:** chỉ tạo trang cho nơi bạn thật sự phục vụ, kèm thông tin riêng (địa chỉ chi nhánh, thời gian đến nơi, giá theo khu vực, ảnh thật, đánh giá khách khu vực đó). Lưu ý các đợt sắp xếp lại đơn vị hành chính — dùng tên địa danh hiện hành và cách người dân vẫn gọi (ví dụ tên quận cũ còn được tìm nhiều) cho đúng thực tế tìm kiếm.

---

## Khung triển khai

1. **Nghiên cứu mẫu từ khóa:** cấu trúc lặp lại là gì; biến là gì; bao nhiêu tổ hợp. Xác nhận nhu cầu: tổng lượng tìm, phân bổ (đầu vs. đuôi dài), xu hướng. Lưu ý người Việt gõ cả có dấu lẫn không dấu.
2. **Dữ liệu:** dữ liệu nào điền vào mỗi trang; tự có, thu thập, mua bản quyền hay công khai; cập nhật thế nào. Thu thập dữ liệu từ web khác: tôn trọng điều khoản sử dụng và quyền sở hữu trí tuệ; không thu thập dữ liệu cá nhân.
3. **Thiết kế mẫu trang:** tiêu đề có từ khóa đích; đoạn mở đầu riêng (không chỉ thay biến); các phần dựa trên dữ liệu; trang liên quan/link nội bộ; CTA hợp ý định. **Bảo đảm khác biệt:** nội dung có điều kiện theo dữ liệu; nhận xét/phân tích riêng mỗi trang.
4. **Liên kết nội bộ:** trang trung tâm (danh mục) + trang vệ tinh (từng trang chương trình) + link chéo giữa vệ tinh liên quan. Không trang mồ côi: mọi trang đến được từ trang chính, có trong sitemap, có breadcrumb kèm dữ liệu có cấu trúc.
5. **Chiến lược lập chỉ mục:** ưu tiên mẫu lượng tìm cao; noindex biến thể quá mỏng; quản lý ngân sách thu thập; sitemap riêng theo loại trang.
6. **Chọn nền tảng xây:** kiểm nền tảng chứa được số trang, cập nhật dữ liệu, xuất HTML phía máy chủ, rẽ nhánh nội dung theo dữ liệu, điều khiển lập chỉ mục từng trang. Ưu tiên CMS hiện có nếu đủ sức; không thì phục vụ bộ trang trên đường dẫn con của tên miền chính. Lựa chọn và đánh đổi: [references/implementation-platforms.md](references/implementation-platforms.md).

## Kiểm tra chất lượng

**Trước khi ra mắt:**
- Nội dung: mỗi trang có giá trị riêng; đáp ứng ý định; dễ đọc, hữu ích; tiếng Việt tự nhiên (không văn ghép biến cứng nhắc như "Dịch vụ sửa máy lạnh tại Quận 7 uy tín chất lượng giá rẻ")
- Kỹ thuật: tiêu đề và mô tả meta duy nhất; đề mục đúng; có schema; tốc độ ổn
- Liên kết: nối vào cấu trúc site; link trang liên quan; không mồ côi
- Lập chỉ mục: có trong sitemap; thu thập được; không noindex xung đột

**Sau ra mắt theo dõi:** tỷ lệ được lập chỉ mục, thứ hạng, traffic, tương tác, chuyển đổi. Cảnh giác: cảnh báo nội dung mỏng, tụt hạng, hình phạt thủ công, lỗi thu thập.

**Thử trước khi nhân rộng:** ra mắt một lô nhỏ (vài chục trang), đo tỷ lệ lập chỉ mục và hiệu quả sau vài tuần, rồi mới mở rộng.

## Lỗi thường gặp

- **Nội dung mỏng:** chỉ thay tên quận/tỉnh trong nội dung giống hệt
- **Ăn thịt từ khóa:** nhiều trang nhắm cùng một từ
- **Tạo thừa:** làm trang không có nhu cầu tìm kiếm
- **Dữ liệu kém:** lỗi thời hoặc sai
- **Bỏ qua trải nghiệm:** trang làm cho Google chứ không cho người

## Định dạng đầu ra

**Tài liệu chiến lược:** phân tích cơ hội; kế hoạch triển khai; hướng dẫn nội dung.
**Mẫu trang:** cấu trúc URL; mẫu tiêu đề/meta (tiếng Việt tự nhiên); dàn ý nội dung kèm phần nào là dữ liệu, phần nào viết riêng; schema.

## Câu hỏi theo việc

1. Nhắm những mẫu từ khóa nào?
2. Đang có (hoặc có thể có) dữ liệu gì?
3. Dự định bao nhiêu trang?
4. Độ uy tín của tên miền hiện tại?
5. Ai đang lên top cho các từ này?
6. Nền tảng kỹ thuật đang dùng?

## Skill liên quan

- `seo-audit` — kiểm tra các trang sau ra mắt
- `schema` — dữ liệu có cấu trúc
- `site-architecture` — phân cấp, URL, liên kết nội bộ
- `local-marketing` — trang chi nhánh, SEO địa phương
- `competitors` — khung trang so sánh (lưu ý pháp lý)
- `free-tools` — công cụ tính toán làm trang chương trình
