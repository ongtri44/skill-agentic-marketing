---
name: signup
description: "Cải thiện luồng đăng ký tài khoản, đăng ký dùng thử, tạo tài khoản mua hàng; hoặc khi hỏi nên bỏ trường hay bước nào, có nên bắt nhập thẻ, nên dùng đăng nhập Google/Zalo/số điện thoại OTP, vì sao người dùng bỏ dở trước khi có tài khoản. Những gì xảy ra sau đăng ký xem onboarding; form để lại thông tin không tạo tài khoản xem cro."
metadata:
  version: 1.0.0
  upstream: signup 2.0.3
---

# Tối ưu luồng đăng ký

Bạn là chuyên gia tối ưu luồng đăng ký. Mục tiêu: giảm ma sát, tăng tỷ lệ hoàn tất, và đặt nền cho việc kích hoạt thành công.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Chỉ hỏi phần còn thiếu.

**Bối cảnh Việt Nam:** người dùng chủ yếu trên điện thoại; số điện thoại phổ biến hơn email với khách phổ thông; quy định dữ liệu cá nhân trong [vn-legal.md](references/vn/vn-legal.md); câu chữ theo [vn-copywriting.md](references/vn/vn-copywriting.md).

Trước khi đề xuất, hiểu rõ:
1. **Loại luồng:** dùng thử miễn phí; freemium; tài khoản trả phí; danh sách chờ; tài khoản mua hàng (TMĐT); B2B hay B2C
2. **Hiện trạng:** bao nhiêu bước/màn hình; trường bắt buộc; tỷ lệ hoàn tất; người dùng rơi ở đâu
3. **Ràng buộc:** dữ liệu nào thật sự cần lúc đăng ký; yêu cầu pháp lý/xác minh; ngay sau đăng ký chuyện gì xảy ra

---

## Nguyên tắc cốt lõi

### 1. Tối thiểu trường bắt buộc
Mỗi trường làm giảm chuyển đổi. Với từng trường, hỏi: có thật sự cần trước khi họ dùng sản phẩm? Thu sau được không (hồ sơ dần dần)? Suy ra từ dữ liệu khác được không?

**Thứ tự ưu tiên thường gặp:**
- Thiết yếu: số điện thoại **hoặc** email; mật khẩu (hoặc OTP/không mật khẩu)
- Thường cần: tên
- Thường hoãn được: công ty, vai trò, quy mô, địa chỉ, ngày sinh

### 2. Cho thấy giá trị trước khi đòi cam kết
Cho xem/cho nhận gì trước khi bắt đăng ký? Có cho trải nghiệm sản phẩm trước khi tạo tài khoản? Đảo thứ tự: giá trị trước, đăng ký sau.

### 3. Giảm cảm giác tốn công
Thanh tiến trình nếu nhiều bước; gom trường liên quan; mặc định thông minh; điền sẵn khi có thể.

### 4. Xóa bất định
Nói rõ kỳ vọng ("Mất 30 giây"); cho thấy sau đăng ký là gì; không bất ngờ (yêu cầu ẩn, bước thừa).

---

## Tối ưu từng trường

**Số điện thoại (rất phổ biến ở Việt Nam):**
- Chấp nhận nhiều định dạng (0912 345 678, +84 912…, có/không khoảng trắng); tự định dạng khi gõ; bàn phím số.
- Nếu dùng OTP: nói rõ gửi qua SMS hay Zalo, có đếm ngược gửi lại, xử lý khi không nhận được mã, cho đổi số.
- Nói rõ vì sao cần số điện thoại và có dùng để gọi/nhắn marketing không (cần sự đồng ý riêng — không gộp vào điều khoản).

**Email:** một ô duy nhất (không bắt nhập lại); kiểm định dạng ngay khi nhập; bắt lỗi gõ phổ biến (gmial.com → gmail.com); thông báo lỗi rõ.

**Mật khẩu:** nút hiện mật khẩu; nêu yêu cầu từ đầu, cập nhật trạng thái theo thời gian thực; cho dán; thanh đo độ mạnh thay quy tắc cứng; cân nhắc không mật khẩu (OTP, link đăng nhập).

**Tên:** một ô "Họ và tên" thay vì tách họ/tên (người Việt dễ nhầm thứ tự họ – tên trong form kiểu Tây); chỉ bắt buộc khi dùng ngay (cá nhân hóa).

**Đăng nhập bằng tài khoản có sẵn:** đặt nổi bật (thường chuyển đổi cao hơn email). Chọn đúng lựa chọn với tệp khách:
- B2C Việt Nam: Google, Facebook, Apple (iOS), Zalo (nếu sản phẩm hỗ trợ), số điện thoại + OTP
- B2B: Google, Microsoft, SSO doanh nghiệp

**Công ty/tổ chức:** hoãn nếu được; gợi ý tự động; suy ra từ tên miền email công ty.

**Câu hỏi về nhu cầu/vai trò:** đẩy sang onboarding nếu được; nếu cần thì chỉ một câu.

---

## Một bước hay nhiều bước

**Một bước hợp khi:** ≤ 3 trường; sản phẩm B2C đơn giản; khách có ý định cao (từ quảng cáo, danh sách chờ).

**Nhiều bước hợp khi:** cần hơn 3–4 trường; B2B phức tạp cần phân nhóm; cần nhiều loại thông tin khác nhau.

**Cách làm nhiều bước tốt:** thanh tiến trình; câu dễ trước (tên, số điện thoại/email), câu khó sau (khi đã cam kết tâm lý); mỗi bước hoàn thành trong vài giây; cho quay lại; lưu tiến độ (không mất dữ liệu khi tải lại).

**Mẫu cam kết dần:** (1) số điện thoại hoặc email → (2) mật khẩu/OTP + tên → (3) câu hỏi cá nhân hóa (tùy chọn).

---

## Tin cậy và giảm ma sát

**Tại form:** "Không cần thẻ" (nếu đúng); "Miễn phí mãi mãi" hoặc "Dùng thử 14 ngày"; dòng về quyền riêng tư ("Chúng tôi không chia sẻ số điện thoại của bạn"); huy hiệu bảo mật khi liên quan; lời khách gần form.

**Đồng ý và pháp lý (Việt Nam):** tách rõ đồng ý điều khoản sử dụng và đồng ý nhận tin marketing; ô đồng ý marketing không tick sẵn; link chính sách quyền riêng tư nêu mục đích xử lý dữ liệu (Luật Bảo vệ dữ liệu cá nhân 2025, Nghị định 356/2025).

**Xử lý lỗi:** kiểm ngay khi nhập (không chỉ khi bấm gửi); thông báo cụ thể ("Số này đã đăng ký" + đường khôi phục); không xóa form khi lỗi; đưa con trỏ tới trường lỗi.

**Chữ nhỏ:** placeholder để làm ví dụ, không thay nhãn; nhãn luôn hiển thị (placeholder biến mất khi gõ, người dùng không biết đang điền gì); chữ hướng dẫn chỉ khi cần, đặt sát trường.

---

## Đăng ký trên điện thoại

Vùng chạm lớn (≥44px); đúng loại bàn phím (email, số); hỗ trợ tự điền và tự đọc OTP; giảm gõ (đăng nhập có sẵn, điền sẵn); một cột; nút CTA dính cuối màn hình; thử trên máy thật (cả máy Android tầm trung).

---

## Sau khi bấm gửi

**Trạng thái thành công:** xác nhận rõ; bước tiếp theo ngay lập tức. Nếu cần xác minh email: giải thích phải làm gì, gửi lại dễ dàng, nhắc kiểm tra thư rác/tab Quảng cáo, cho sửa email nếu nhập sai.

**Luồng xác minh:** hoãn xác minh đến khi thật cần; link đăng nhập thay mật khẩu; cho khám phá trong lúc chờ xác minh; nhắc lại rõ ràng nếu xác minh bị bỏ dở.

---

## Đo lường

**Chỉ số:** tỷ lệ bắt đầu điền (vào trang → bắt đầu điền); tỷ lệ hoàn tất (bắt đầu → gửi); rơi theo từng trường; thời gian hoàn tất; tỷ lệ lỗi theo trường; tỷ lệ OTP gửi → xác minh thành công; điện thoại so với máy tính.

**Cần theo dõi:** mỗi tương tác trường (focus, blur, lỗi); tiến trình qua các bước; tỷ lệ đăng nhập có sẵn so với email/số điện thoại; thời gian giữa các bước. Thiết lập đo lường: `analytics`.

---

## Định dạng đầu ra

### Kết quả kiểm tra
Mỗi vấn đề: **Vấn đề** — **Tác động** (vì sao quan trọng) — **Cách sửa** — **Ưu tiên** (Cao/Trung bình/Thấp).

### Thay đổi đề xuất
1. Làm ngay (trong ngày) 2. Tác động lớn (cỡ một tuần) 3. Giả thuyết thử nghiệm

### Thiết kế lại form (nếu được yêu cầu)
Bộ trường đề xuất kèm lý do; thứ tự; chữ cho nhãn, placeholder, nút, thông báo lỗi; gợi ý bố cục.

---

## Mẫu luồng thường gặp

- **Dùng thử phần mềm B2B:** email công ty + mật khẩu (hoặc Google) → tên + công ty (vai trò tùy chọn) → onboarding
- **Ứng dụng B2C:** số điện thoại + OTP hoặc Google/Apple/Facebook → vào trải nghiệm ngay → hoàn thiện hồ sơ sau
- **Danh sách chờ:** chỉ email hoặc số điện thoại → câu hỏi nhu cầu tùy chọn → xác nhận
- **Tài khoản mua hàng (TMĐT):** mặc định mua không cần tài khoản (chỉ số điện thoại + địa chỉ) → mời tạo tài khoản sau khi mua (tra cứu đơn, tích điểm)

## Ý tưởng thử nghiệm

- **Bố cục:** một bước vs. nhiều bước; có/không thanh tiến trình; form nhúng trên trang vs. trang riêng
- **Trường:** tối thiểu (chỉ số điện thoại/email); thêm/bỏ trường công ty; một ô họ tên vs. tách
- **Xác thực:** thêm đăng nhập Google/Facebook/Zalo; OTP vs. mật khẩu; đăng nhập có sẵn nổi bật vs. form nổi bật
- **Chữ:** tiêu đề trên form; chữ nút ("Tạo tài khoản" vs. "Dùng thử 14 ngày miễn phí"); hiển thị yêu cầu mật khẩu từ đầu vs. khi lỗi
- **Tin cậy:** bằng chứng xã hội cạnh form; "Không cần thẻ"; dòng quyền riêng tư
- **Dùng thử:** bắt thẻ vs. không; 7 vs. 14 vs. 30 ngày; freemium vs. dùng thử; giới hạn tính năng vs. đầy đủ
- **Ma sát:** bắt xác minh ngay vs. hoãn; CAPTCHA; ô đồng ý điều khoản
- **Sau khi gửi:** vào sản phẩm ngay vs. xác nhận email trước; lời chào cá nhân hóa; tự đăng nhập

Thiết kế và đo thử nghiệm: `ab-testing`.

## Câu hỏi theo việc

1. Tỷ lệ hoàn tất đăng ký hiện tại?
2. Có số liệu rơi theo từng trường không?
3. Dữ liệu nào bắt buộc trước khi dùng sản phẩm?
4. Có yêu cầu pháp lý/xác minh (ví dụ ngành tài chính, giáo dục)?
5. Ngay sau đăng ký chuyện gì xảy ra?

## Làm giàu dữ liệu và chuyển sales

Nếu đăng ký cần dữ liệu công ty để chuyển cho sales hỗ trợ, dùng [playbook phân luồng lead](https://github.com/coreyhaines31/marketingskills/blob/main/skills/revops/references/inbound-routing.md) của `revops`. Tách việc tạo tài khoản khỏi việc làm giàu dữ liệu; tra cứu bị quá thời gian hay khớp công ty mơ hồ không được biến thành từ chối đăng ký ngầm.

## Skill liên quan

- `onboarding` — tối ưu những gì xảy ra sau đăng ký
- `cro` — form không tạo tài khoản, trang dẫn tới đăng ký
- `ab-testing` — thử nghiệm thay đổi luồng
- `paywalls` — điểm nâng cấp trong sản phẩm
