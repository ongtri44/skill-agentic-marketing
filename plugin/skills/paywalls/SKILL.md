---
name: paywalls
description: "Tạo hoặc cải thiện màn hình nâng cấp và paywall trong ứng dụng/phần mềm, hoặc khi hỏi nên mời người dùng miễn phí trả tiền lúc nào và mạnh tới đâu (sau khi họ đã thấy giá trị): màn hình nâng cấp, cửa sổ bán thêm, khóa tính năng, hết hạn mức, hết dùng thử, paywall gói thuê bao trên điện thoại. Trang bảng giá công khai xem cro; quyết định giá xem pricing."
metadata:
  version: 1.0.0
  upstream: paywalls 2.1.4
---

# Paywall và màn hình nâng cấp

Bạn là chuyên gia paywall và luồng nâng cấp trong sản phẩm. Mục tiêu: chuyển người dùng miễn phí sang trả phí, hoặc nâng lên gói cao hơn, đúng lúc họ đã trải nghiệm đủ giá trị để đáng cam kết.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Chỉ hỏi phần còn thiếu.

Hiểu rõ:
1. **Bối cảnh nâng cấp:** freemium → trả phí? Dùng thử → trả phí? Nâng gói? Bán thêm tính năng? Hết hạn mức?
2. **Mô hình:** cái gì miễn phí, cái gì sau paywall, điều gì kích hoạt lời mời, tỷ lệ chuyển đổi hiện tại?
3. **Hành trình:** paywall xuất hiện lúc nào, người dùng đã trải nghiệm gì, họ đang cố làm gì?

**Bối cảnh Việt Nam:** người dùng nhạy giá và quen thanh toán qua ví điện tử, chuyển khoản QR, thẻ nội địa; thanh toán thẻ quốc tế định kỳ có thể là rào cản với một phần khách. Cân nhắc gói trả trước 3/6/12 tháng, thanh toán qua ví/QR, xuất hóa đơn VAT cho khách doanh nghiệp. Tránh mọi "mẫu tối" (dark pattern) — vừa mất niềm tin, vừa có thể vi phạm quy định bảo vệ người tiêu dùng.

---

## Nguyên tắc

1. **Giá trị trước, lời mời sau.** Người dùng phải trải nghiệm giá trị thật trước; nâng cấp nên là bước tiếp theo tự nhiên; thời điểm: sau khoảnh khắc aha, không phải trước.
2. **Cho thấy, đừng chỉ kể.** Minh họa giá trị tính năng trả phí; cho xem trước thứ họ đang bỏ lỡ; làm việc nâng cấp trở nên hữu hình.
3. **Đường đi không ma sát.** Dễ nâng cấp khi sẵn sàng; đừng bắt đi tìm bảng giá.
4. **Tôn trọng lời từ chối.** Không nhốt, không ép; dễ tiếp tục dùng miễn phí; giữ niềm tin cho lần chuyển đổi sau.

## Điểm kích hoạt paywall

- **Khóa tính năng** (bấm vào tính năng chỉ có ở gói trả phí): giải thích rõ vì sao trả phí; cho thấy tính năng làm gì; đường mở khóa nhanh; lựa chọn tiếp tục mà không cần.
- **Hết hạn mức:** báo rõ đã chạm hạn mức; cho thấy nâng cấp được gì; đừng chặn đột ngột (cho hoàn tất việc đang dở nếu có thể).
- **Hết dùng thử:** báo trước (7, 3, 1 ngày); nói rõ chuyện gì xảy ra khi hết hạn (dữ liệu có mất không); tóm tắt giá trị đã nhận.
- **Theo thời gian:** sau X ngày dùng miễn phí — nhắc nhẹ, nêu tính năng trả phí chưa dùng, dễ tắt.

## Thành phần màn hình paywall

1. **Tiêu đề** — nói thứ họ nhận: "Mở khóa [tính năng] để [lợi ích]"
2. **Minh họa giá trị** — xem trước, trước/sau, "Với gói Pro, bạn có thể…"
3. **So sánh gói** — nêu khác biệt chính, đánh dấu gói hiện tại
4. **Giá** — rõ, đơn giản, theo tháng và theo năm (ghi rõ số tiền tiết kiệm), đã gồm hay chưa gồm VAT
5. **Bằng chứng xã hội** — lời khách, "X doanh nghiệp đang dùng"
6. **CTA** — cụ thể, hướng giá trị: "Bắt đầu [lợi ích]"
7. **Lối thoát** — "Để sau" hoặc "Tiếp tục bản miễn phí" rõ ràng

## Mẫu paywall

**Khóa tính năng**
```
[Biểu tượng khóa]
Tính năng này có trong gói Pro
[Ảnh xem trước tính năng]
[Tên tính năng] giúp bạn [lợi ích]:
• [Khả năng]
• [Khả năng]
[Nâng cấp Pro – 199.000đ/tháng]
[Để sau]
```

**Hết hạn mức**
```
Bạn đã dùng hết hạn mức miễn phí
[Thanh tiến độ 100%]
Miễn phí: 3 cửa hàng | Pro: không giới hạn
[Nâng cấp Pro]  [Xóa bớt một cửa hàng]
```

**Hết dùng thử**
```
Thời gian dùng thử còn 3 ngày
Bạn sẽ mất quyền dùng:
• [Tính năng đã dùng]
• [Dữ liệu đã tạo — giữ trong 30 ngày]
Bạn đã làm được:
• Tạo 42 đơn hàng, tiết kiệm ~6 giờ đối soát
[Tiếp tục với Pro]
[Nhắc tôi sau]  [Chuyển về bản miễn phí]
```

## Thời điểm và tần suất

**Nên hiện:** sau khoảnh khắc giá trị, trước khi bực bội; sau kích hoạt; khi chạm giới hạn thật.
**Không nên hiện:** trong onboarding (quá sớm); khi họ đang làm dở một việc; lặp lại sau khi đã tắt.
**Quy tắc:** giới hạn mỗi phiên; thời gian chờ sau khi tắt (tính bằng ngày, không phải giờ); theo dõi dấu hiệu khó chịu.

## Luồng nâng cấp

**Từ paywall tới thanh toán:** ít bước nhất; giữ trong ngữ cảnh nếu được; điền sẵn thông tin đã biết; hỗ trợ phương thức thanh toán quen thuộc (ví, QR, thẻ nội địa, thẻ quốc tế); có lựa chọn xuất hóa đơn công ty.
**Sau nâng cấp:** truy cập tính năng ngay; xác nhận và hóa đơn/biên nhận; hướng dẫn tính năng mới.

## Thử nghiệm

**Thử:** thời điểm kích hoạt; tiêu đề/chữ; cách trình bày giá (tháng/năm, giá theo ngày); thời gian dùng thử; tính năng được nhấn mạnh; thiết kế.
**Đo:** tỷ lệ hiển thị paywall; tỷ lệ bấm nâng cấp; tỷ lệ hoàn tất thanh toán; doanh thu mỗi người dùng; tỷ lệ hủy sau nâng cấp.

Ý tưởng đầy đủ: [references/experiments.md](references/experiments.md). **Ứng dụng thuê bao iOS/Android** (paywall trong onboarding, ưu tiên gói năm, dùng thử và nhắc nhở, phí cửa hàng ứng dụng, thanh toán qua web, doanh thu mỗi lượt tải): [references/mobile-subscription-paywalls.md](references/mobile-subscription-paywalls.md) (tiếng Anh; kiểm tra chính sách cửa hàng ứng dụng hiện hành tại Việt Nam).

## Những điều phải tránh

**Mẫu tối:** giấu nút đóng; chọn gói gây nhầm lẫn; chữ gây cảm giác tội lỗi; đồng hồ đếm ngược giả, ưu đãi "giới hạn" không có hạn thật; tự gia hạn không báo trước; khó hủy.
**Giết chuyển đổi:** hỏi trước khi trao giá trị; nhắc quá dày; chặn luồng quan trọng; quy trình nâng cấp rườm rà.

## Câu hỏi theo việc

1. Tỷ lệ miễn phí → trả phí hiện tại?
2. Điều gì đang kích hoạt lời mời nâng cấp?
3. Tính năng nào sau paywall?
4. Khoảnh khắc aha của người dùng là gì?
5. Mô hình giá (theo người dùng, theo mức dùng, cố định)?
6. Ứng dụng điện thoại, web, hay cả hai? Phương thức thanh toán đang hỗ trợ?

## Skill liên quan

- `churn-prevention` — luồng hủy, ưu đãi giữ chân, giảm rời bỏ sau nâng cấp
- `cro` — trang bảng giá công khai
- `onboarding` — đưa người dùng tới khoảnh khắc aha trước khi mời nâng cấp
- `pricing` — quyết định giá và gói
- `ab-testing` — thử nghiệm biến thể paywall
