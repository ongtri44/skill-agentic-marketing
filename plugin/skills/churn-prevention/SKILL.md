---
name: churn-prevention
description: "Giảm tỷ lệ khách rời bỏ và tăng mua lại, hoặc khi hỏi vì sao khách hủy, có nên giảm giá hay cho tạm ngưng: luồng hủy, khảo sát khi rời, ưu đãi giữ chân, nhắc gia hạn gói trả trước, thanh toán thất bại, điểm sức khỏe khách hàng; với bán lẻ, F&B, spa, gym là khách không quay lại, chu kỳ mua lại, phân nhóm RFM. Tin nhắn kéo khách cũ xem emails, zalo; màn hình nâng cấp xem paywalls."
metadata:
  version: 1.0.0
  upstream: churn-prevention 2.0.6
---

# Chống rời bỏ, tăng giữ chân

Bạn là chuyên gia giữ chân khách hàng. Mục tiêu: giảm rời bỏ **chủ động** (khách tự hủy/không quay lại) và **bị động** (thanh toán thất bại, quên gia hạn) bằng luồng hủy tốt, ưu đãi giữ chân đúng lý do, giữ chân chủ động và quy trình thu hồi thanh toán.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

**Bối cảnh Việt Nam:** nhiều khách trả trước theo gói (tháng/quý/năm) bằng chuyển khoản thay vì thẻ tự gia hạn — "rời bỏ" thường là **không gia hạn**, nên nhắc gia hạn quan trọng hơn thu hồi thẻ lỗi. Kênh chăm sóc hiệu quả thường là Zalo (OA, ZNS, nhóm hỗ trợ) và cuộc gọi của người phụ trách. Đừng làm khó việc hủy — vừa mất niềm tin, vừa có thể vi phạm quy định bảo vệ người tiêu dùng ([vn-legal.md](references/vn/vn-legal.md)).

Thu thập:
1. **Tình hình:** tỷ lệ rời bỏ hằng tháng (chủ động/bị động nếu biết); số khách đang hoạt động; doanh thu trung bình mỗi khách; hiện có luồng hủy chưa hay hủy ngay
2. **Thanh toán:** thẻ tự gia hạn (Stripe, cổng nội địa…) hay chuyển khoản/trả trước; chu kỳ tháng/năm; có cho tạm ngưng hoặc hạ gói không; công cụ giữ chân đang dùng
3. **Dữ liệu sử dụng:** có theo dõi tính năng theo người dùng; nhận ra sụt tương tác được không; có dữ liệu lý do hủy cũ; chỉ số kích hoạt (khách ở lại làm gì mà khách rời không làm)
4. **Ràng buộc:** B2B hay B2C; giọng điệu khi khách rời
5. **Không phải thuê bao?** (bán lẻ, F&B, spa, phòng khám, gym theo buổi) → xem phần "Giữ chân khi không có thuê bao" ở cuối

---

## Hai loại rời bỏ

| Loại | Nguyên nhân | Giải pháp |
|---|---|---|
| **Chủ động** | Khách chọn hủy/không gia hạn | Luồng hủy, ưu đãi giữ chân, khảo sát khi rời, giữ chân chủ động |
| **Bị động** | Thẻ lỗi, quên chuyển khoản gia hạn | Nhắc trước hạn, thử thu lại, chuỗi tin nhắc, thời gian ân hạn |

Rời bỏ bị động thường chiếm phần đáng kể và dễ sửa hơn. Ba chế độ: (1) xây luồng hủy; (2) tối ưu luồng hiện có từ dữ liệu; (3) thiết lập thu hồi thanh toán/nhắc gia hạn.

---

## Luồng hủy

```
Kích hoạt → Khảo sát → Ưu đãi theo lý do → Xác nhận → Sau khi hủy
```
1. **Kích hoạt:** khách bấm "Hủy gói" (hoặc nhắn yêu cầu hủy qua Zalo/hotline — quy trình tương tự do người phụ trách thực hiện).
2. **Khảo sát khi rời:** hỏi lý do → quyết định ưu đãi nào hiện ra.
3. **Ưu đãi theo lý do** (giảm giá, tạm ngưng, hạ gói…).
4. **Xác nhận:** nếu vẫn hủy, xác nhận rõ, nói rõ quyền dùng đến hết kỳ đã trả.
5. **Sau khi hủy:** đặt kỳ vọng (dữ liệu giữ bao lâu), đường kích hoạt lại dễ dàng, chuỗi tin kéo lại.

### Khảo sát khi rời

| Lý do | Cho biết |
|---|---|
| Đắt quá | Nhạy giá — có thể phản hồi với giảm giá/hạ gói |
| Không dùng nhiều | Tương tác thấp — tạm ngưng hoặc hỗ trợ onboarding |
| Thiếu tính năng | Khoảng trống sản phẩm — lộ trình hoặc cách làm thay |
| Chuyển sang lựa chọn khác | Áp lực cạnh tranh — tìm hiểu họ đưa ra gì |
| Lỗi kỹ thuật | Chất lượng — chuyển hỗ trợ ngay |
| Nhu cầu tạm thời/theo mùa | Mẫu sử dụng — tạm ngưng |
| Đóng cửa/đổi mô hình kinh doanh | Không tránh được — học và để khách đi nhẹ nhàng |
| Khác | Có ô nhập tự do |

Một câu hỏi, chọn một, có ô tự do; tối đa 5–8 lựa chọn; lý do phổ biến lên đầu (xem lại mỗi quý); không gây cảm giác tội lỗi; "Giúp chúng tôi làm tốt hơn" tốt hơn "Vì sao bạn bỏ đi?".

### Ưu đãi theo lý do

**Cốt lõi: khớp ưu đãi với lý do.** Giảm giá không giữ được người không dùng; lộ trình tính năng không giữ được người không đủ tiền.

| Lý do | Ưu đãi chính | Dự phòng |
|---|---|---|
| Đắt quá | Giảm 20–30% trong 2–3 tháng | Hạ gói |
| Không dùng nhiều | Tạm ngưng 1–3 tháng | Buổi hỗ trợ sử dụng miễn phí (gọi/Zalo) |
| Thiếu tính năng | Xem trước lộ trình + thời gian | Hướng dẫn cách làm thay |
| Chuyển sang lựa chọn khác | Buổi trao đổi lấy phản hồi + ưu đãi | — |
| Lỗi kỹ thuật | Chuyển hỗ trợ ngay | Bù thời gian sử dụng + ưu tiên sửa |
| Tạm thời/theo mùa | Tạm ngưng | Hạ gói tạm thời |
| Đóng cửa | Bỏ qua ưu đãi (tôn trọng hoàn cảnh) | — |

**Các loại ưu đãi:**
- **Giảm giá:** 20–30% trong 2–3 tháng là vùng hợp lý; tránh 50%+ (dạy khách hủy để được giảm); nêu số tiền tiết kiệm cụ thể (VND), không chỉ %; nếu nói "ưu đãi hết khi rời trang" thì phải đúng như vậy.
- **Tạm ngưng:** tối đa 1–3 tháng (dài hơn hiếm khi quay lại); tự kích hoạt lại kèm tin báo trước; giữ nguyên dữ liệu.
- **Hạ gói:** cho thấy giữ được gì, mất gì; gọi là "chọn gói vừa với nhu cầu"; đường nâng lại dễ dàng.
- **Mở khóa tính năng/gia hạn dùng thử gói cao:** hợp với lý do "chưa thấy đủ giá trị".
- **Liên hệ cá nhân:** cho 10–20% khách giá trị cao nhất — người phụ trách gọi/nhắn Zalo; công ty nhỏ — chủ doanh nghiệp tự liên hệ.

### Mẫu giao diện
```
┌─────────────────────────────────────┐
│  Tiếc quá khi anh/chị muốn dừng     │
│  Lý do chính là gì ạ?               │
│  ○ Chi phí chưa phù hợp             │
│  ○ Chưa dùng nhiều                  │
│  ○ Thiếu tính năng cần              │
│  ○ Chuyển sang công cụ khác         │
│  ○ Gặp lỗi kỹ thuật                 │
│  ○ Tạm thời chưa cần                │
│  ○ Khác: [____________]             │
│  [Tiếp tục]                         │
│  [Thôi, giữ gói của tôi]            │
└─────────────────────────────────────┘
        ↓ (chọn "Chi phí chưa phù hợp")
┌─────────────────────────────────────┐
│  Bên em hỗ trợ thế này được không?  │
│  ┌───────────────────────────────┐  │
│  │ Giảm 25% trong 3 tháng tới    │  │
│  │ Tiết kiệm 150.000đ/tháng      │  │
│  │ [Nhận ưu đãi]                 │  │
│  └───────────────────────────────┘  │
│  Hoặc chuyển sang gói Cơ bản        │
│  299.000đ/tháng →                   │
│  [Không, tiếp tục hủy]              │
└─────────────────────────────────────┘
```
**Nguyên tắc:** luôn để lựa chọn "tiếp tục hủy" hiển thị (không mẫu tối); một ưu đãi chính + một dự phòng; số tiền cụ thể; dùng tên và dữ liệu tài khoản; tốt trên điện thoại. Mẫu theo ngành và nhà cung cấp thanh toán: [references/cancel-flow-patterns.md](references/cancel-flow-patterns.md) (tiếng Anh).

---

## Dự báo rời bỏ và giữ chân chủ động

Giữ chân tốt nhất xảy ra trước khi khách bấm "Hủy".

| Tín hiệu | Mức rủi ro | Thời gian trước khi hủy |
|---|---|---|
| Tần suất đăng nhập giảm 50%+ | Cao | 2–4 tuần |
| Ngừng dùng tính năng chính | Cao | 1–3 tuần |
| Yêu cầu hỗ trợ tăng vọt rồi im bặt | Cao | 1–2 tuần |
| Không đọc tin nhắn/email | Trung bình | 2–6 tuần |
| Xem trang thanh toán/gói nhiều hơn | Cao | Vài ngày |
| Xóa bớt tài khoản người dùng | Cao | 1–2 tuần |
| Xuất dữ liệu | Rất cao | Vài ngày |
| Điểm giới thiệu cá nhân 0–6 | Trung bình | 1–3 tháng |
| (Trả trước) Còn 30 ngày hết hạn, chưa phản hồi nhắc gia hạn | Cao | Đến hạn |

### Điểm sức khỏe khách hàng
Điểm 0–100 từ các tín hiệu có trọng số. Đưa **mọi thành phần về cùng thang 0–100** (cao = khỏe) trước khi nhân trọng số; dùng ánh xạ ghi rõ cho từng loại dữ liệu thô — không cộng thẳng số lần đăng nhập với điểm cảm nhận 1–5. Trọng số dưới đây chỉ là điểm khởi đầu minh họa.

Tín hiệu thiếu hoặc cũ coi là **không có**, không phải tự động khỏe hay bằng 0. Đặt cửa sổ độ mới và mức phủ tối thiểu trước khi dùng. Nếu cho phép điểm một phần: `tổng(trọng số × điểm quan sát) / tổng(trọng số đã quan sát)` và báo kèm mức phủ; nếu không thì trả "không đủ dữ liệu". Ví dụ chỉ có đăng nhập (80) và tính năng (60): `(0,30×80 + 0,25×60)/0,55 = 70,91`, phủ 55%.

```
Điểm sức khỏe = Đăng nhập × 0,30 + Dùng tính năng × 0,25 + Cảm nhận hỗ trợ × 0,15
              + Sức khỏe thanh toán × 0,15 + Tương tác × 0,15
```
Kiểm ánh xạ và ngưỡng với kết quả gia hạn/rời bỏ thực tế trước khi dùng vận hành. Ngưỡng minh họa: 80–100 khỏe (cơ hội bán thêm); 60–79 cần chú ý (hỏi thăm chủ động); 40–59 rủi ro (chiến dịch can thiệp); 0–39 nguy cấp (liên hệ cá nhân).

### Can thiệp chủ động

| Kích hoạt | Can thiệp |
|---|---|
| Sử dụng giảm >50% trong 2 tuần | Tin "Thấy anh/chị chưa dùng [tính năng], cần bên em hỗ trợ không?" |
| Sắp chạm hạn mức | Gợi ý nâng gói (nhẹ nhàng — xem `paywalls`) |
| 14 ngày không đăng nhập | Tin kéo lại kèm cập nhật sản phẩm mới |
| Điểm giới thiệu 0–6 | Liên hệ cá nhân trong 24 giờ |
| Yêu cầu hỗ trợ chưa xong >48 giờ | Chuyển cấp + cập nhật chủ động |
| Còn 30 ngày đến hạn gia hạn | Tin tổng kết giá trị đã nhận + nhắc gia hạn |

---

## Rời bỏ bị động: nhắc gia hạn và thu hồi thanh toán

### Gói trả trước, chuyển khoản (phổ biến ở Việt Nam)
- **Nhắc trước hạn:** 14, 7, 3, 1 ngày — qua Zalo ZNS/email, kèm **mã QR/thông tin chuyển khoản sẵn nội dung**, link thanh toán ví/thẻ, hóa đơn VAT nếu cần.
- **Tổng kết giá trị** trong tin nhắc (đã xử lý bao nhiêu đơn, tiết kiệm bao nhiêu giờ…).
- **Thời gian ân hạn** ngắn (ví dụ 3–7 ngày) trước khi khóa; báo rõ dữ liệu được giữ bao lâu.
- **Người phụ trách gọi** với khách giá trị cao chưa gia hạn.
- **Ưu đãi gia hạn dài hơn** (năm thay vì tháng) thay vì giảm giá chung.

### Thanh toán thẻ tự gia hạn
```
Phòng ngừa → Thử thu lại thông minh → Chuỗi tin nhắc → Ân hạn → Hủy
```
- **Phòng ngừa:** nhắc thẻ sắp hết hạn (30, 15, 7 ngày); xin phương thức dự phòng; dịch vụ cập nhật thẻ; báo trước 3–5 ngày với gói năm.
- **Thử lại theo loại từ chối:** từ chối tạm thời (không đủ tiền, hết thời gian chờ) → thử lại 3–5 lần trong 7–10 ngày; từ chối vĩnh viễn (thẻ mất, tài khoản đóng) → không thử lại, xin thẻ mới; cần xác thực (3D Secure/OTP) → đưa khách tới trang cập nhật.
- **Nhịp thử:** sau 24 giờ, ngày 3, ngày 5, ngày 7 (kèm tin nhắc mạnh hơn); sau 4 lần → hủy kèm đường kích hoạt lại. Thử lại vào ngày trong tháng từng thanh toán thành công.

**Chuỗi tin nhắc:** ngày 0 (thân thiện: "Thanh toán chưa thành công, anh/chị cập nhật giúp em"); ngày 3 (nhắc hỗ trợ); ngày 7 (khẩn: "Tài khoản sẽ tạm khóa sau 3 ngày"); ngày 10 (lần cuối). Link thẳng tới trang cập nhật (không cần đăng nhập nếu được); nêu điều họ sẽ mất; không đổ lỗi; có kênh hỗ trợ; tin dạng chữ đơn giản thường hiệu quả hơn tin thiết kế.

Playbook đầy đủ theo nhà cung cấp: [references/dunning-playbook.md](references/dunning-playbook.md). Mốc tham khảo quốc tế: thu hồi từ chối tạm thời tốt ≥70%; tổng thu hồi tốt ≥60%.

---

## Giữ chân khi không có thuê bao (bán lẻ, F&B, spa, gym, phòng khám)

"Rời bỏ" ở đây là **khách không quay lại**.
- **Chu kỳ mua lại:** xác định chu kỳ tự nhiên (mỹ phẩm 30–60 ngày, thực phẩm chức năng theo liệu trình, cắt tóc 4–6 tuần, nha khoa 6 tháng). Nhắc đúng lúc sắp hết, không spam.
- **Phân nhóm RFM** (Gần đây – Tần suất – Giá trị): khách VIP (giữ bằng đặc quyền, không phải giảm giá); khách đang nguội (nhắc nhẹ + gợi ý mới); khách đã ngủ (một lần kéo lại có ưu đãi, rồi thôi). Tính bằng code từ dữ liệu đơn hàng.
- **Chương trình thành viên/tích điểm:** đơn giản, dễ hiểu; thể lệ rõ ràng (xem `local-marketing`).
- **Sau mua:** hướng dẫn dùng, hỏi thăm, xử lý khiếu nại nhanh — khách gặp vấn đề được xử lý tốt thường trung thành hơn.
- **Gói trả trước** (thẻ tập, liệu trình): nhắc buổi còn lại, nhắc hết hạn, gia hạn có ưu đãi.
- Kênh: Zalo OA/ZNS, SMS (đã đồng ý), email, gọi điện (khách VIP). Xem `zalo`, `emails`, `sms`.

---

## Đo lường

| Chỉ số | Công thức | Mục tiêu tham khảo |
|---|---|---|
| Tỷ lệ rời bỏ tháng | Khách rời / khách đầu tháng | Tùy ngành; theo xu hướng |
| Rời bỏ doanh thu ròng | (Doanh thu mất − doanh thu mở rộng) / doanh thu đầu kỳ | Âm (mở rộng ròng) |
| Tỷ lệ gia hạn (trả trước) | Khách gia hạn / khách đến hạn | Theo nhóm |
| Tỷ lệ giữ được trong luồng hủy | Giữ được / phiên hủy | 25–35% (quốc tế) |
| Tỷ lệ nhận ưu đãi | Nhận / được đề xuất | 15–25% |
| Tỷ lệ quay lại sau tạm ngưng | Kích hoạt lại / đã tạm ngưng | 60–80% |
| Tỷ lệ thu hồi thanh toán | Thu được / thanh toán lỗi | 50–60% |
| Tỷ lệ mua lại (bán lẻ) | Khách mua lần 2 trong 30/60/90 ngày | Theo ngành |

**Phân tích theo nhóm:** kênh thu hút (kênh nào mang khách bền hơn); loại gói; thời gian gắn bó (hủy nhiều nhất ở mốc nào); lý do hủy (lý do nào đang tăng); loại ưu đãi (ưu đãi nào hiệu quả với nhóm nào). Tính bằng code từ dữ liệu, chỉ so trên các cửa sổ đã khép lại.

**Thử nghiệm luồng hủy** (một biến mỗi lần): mức giảm 20% vs 30% (tỷ lệ giữ, tác động LTV); tạm ngưng 1 vs 3 tháng; khảo sát trước vs sau ưu đãi; cửa sổ vs toàn trang; giọng đồng cảm vs trực tiếp. Thiết kế: `ab-testing`.

## Lỗi thường gặp

- Không có luồng hủy — một khảo sát + một ưu đãi đã giữ được một phần
- Giấu nút hủy — gây bực bội, đánh giá xấu, rủi ro pháp lý
- Một ưu đãi cho mọi lý do
- Giảm giá quá sâu
- Bỏ qua rời bỏ bị động / không nhắc gia hạn
- Chữ gây cảm giác tội lỗi
- Không theo dõi LTV sau khi "giữ được" — khách hủy sau 30 ngày thì chưa thật sự giữ được
- Tạm ngưng quá dài
- Không có đường quay lại sau hủy

## Công cụ

Nền tảng giữ chân (quốc tế): Churnkey, ProsperStack, Raaft, Chargebee Retention. Thanh toán có thử lại/nhắc tự động: Stripe, Chargebee, Paddle, Recurly. Ở Việt Nam: cổng thanh toán nội địa, ví, chuyển khoản QR, kết hợp Zalo ZNS cho nhắc gia hạn. Phân tích: PostHog (thử nghiệm luồng hủy bằng feature flag — [hướng dẫn](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/posthog.md)), Mixpanel, GA4. Danh mục: [tools registry](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md).

## Skill liên quan

- `emails`, `zalo`, `sms` — tin kéo lại, nhắc gia hạn
- `paywalls` — nâng cấp trong app, hết dùng thử
- `pricing` — cấu trúc gói, chiết khấu năm
- `onboarding` — kích hoạt để tránh rời bỏ sớm
- `local-marketing` — khách quen cửa hàng
- `analytics`, `ab-testing` — tín hiệu rời bỏ, thử nghiệm
