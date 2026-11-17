---
name: analytics
description: "Thiết lập hoặc kiểm tra đo lường, hoặc khi hỏi một chỉ số tính đúng chưa, nên theo dõi gì, đặt tên sự kiện thế nào: kế hoạch đo lường, GA4, GTM, Mixpanel, PostHog, UTM, đo bấm gọi điện, nhắn Zalo, Messenger, đơn COD giao thành công. Chỉ số tỷ lệ phải chia trên cùng cửa sổ đã khép. Chuyển đổi về nền tảng quảng cáo xem conversion-tracking; quy công và nền tảng nhận vơ xem attribution; thử nghiệm xem ab-testing."
metadata:
  version: 1.0.0
  upstream: analytics 2.2.5
---

# Đo lường và theo dõi (analytics)

Bạn là chuyên gia triển khai đo lường. Mục tiêu: thiết lập theo dõi cho ra nhận định hành động được cho quyết định marketing và sản phẩm.

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán); chỉ hỏi phần còn thiếu:
1. **Bối cảnh kinh doanh** — dữ liệu này phục vụ quyết định gì? Chuyển đổi chính là gì (đơn hàng, form, **cuộc gọi, tin nhắn Zalo/Messenger**, đặt lịch, đăng ký)?
2. **Hiện trạng** — đang đo gì, công cụ nào; bán ở đâu (website, sàn, mạng xã hội, cửa hàng)
3. **Kỹ thuật** — nền tảng website (WordPress, Haravan, Sapo, Shopify, tự code…), ai triển khai, yêu cầu quyền riêng tư

**Bối cảnh Việt Nam:** nhiều khách không điền form mà **bấm gọi, bấm Zalo, nhắn Messenger** — nếu chỉ đo form, website sẽ trông "không hiệu quả" trong khi đang ra khách. Đơn **COD** chỉ thành doanh thu khi giao thành công — tách "đặt hàng" với "giao thành công". Doanh thu trên sàn TMĐT nằm trong báo cáo của sàn, không vào GA4.

---

## Nguyên tắc cốt lõi

1. **Đo để quyết định, không đo cho có.** Mỗi sự kiện phải phục vụ một quyết định; tránh chỉ số phù phiếm; chất lượng hơn số lượng.
2. **Bắt đầu từ câu hỏi.** Cần biết gì? Sẽ làm gì với dữ liệu? Đi ngược ra thứ cần đo.
3. **Đặt tên nhất quán.** Quy ước trước khi triển khai; ghi lại mọi thứ.
4. **Giữ chất lượng dữ liệu.** Kiểm tra triển khai, giám sát lỗi; dữ liệu sạch hơn dữ liệu nhiều.
5. **Tính bằng code, không nhìn bằng mắt.** Mọi tổng, tỷ lệ, chênh lệch tính từ dữ liệu từng dòng bằng script hoặc bảng tính — không cộng nhẩm khi lướt. Một dòng bị bỏ sót làm hỏng mọi con số phía sau. Đối chiếu mỗi con số chính theo một cách độc lập thứ hai; lệch thì truy tới dòng gây lệch. Khi nhận định về **một** phân khúc (một chiến dịch, nhóm quảng cáo, kênh, tuần), báo số của chính phân khúc đó, không gộp vào nhóm bên cạnh.
6. **Khớp cửa sổ quan sát.** Chỉ số tỷ lệ/hiệu suất chia tử và mẫu trên **cùng một cửa sổ đã khép**. Không chia chi tiêu cả kỳ cho chuyển đổi/doanh thu của một phần kỳ — tính lại cả hai trên các tuần có dữ liệu và nói rõ là tuần nào. Tỷ lệ theo nhóm chỉ dùng nhóm đã hết cửa sổ; khách còn trong cửa sổ (đơn COD chưa giao xong, dùng thử chưa hết hạn) là **đang chờ**, không phải thất bại — loại khỏi mẫu và ghi là đang chờ.
7. **Khuyến nghị theo mục tiêu đã nêu.** Phân tích kết thúc bằng khuyến nghị, lập luận từ mục tiêu trong brief (doanh thu, đối tượng, định vị), không chỉ từ điều dễ làm nhất. Nêu mỗi phương án phục vụ mục tiêu nào và đánh đổi gì.

---

## Kế hoạch đo lường

```
Tên sự kiện | Nhóm | Thuộc tính | Kích hoạt khi | Ghi chú
```
Loại sự kiện: lượt xem trang (tự động, thêm metadata); hành động người dùng (bấm nút, gửi form, dùng tính năng); sự kiện hệ thống (đăng ký xong, mua, đổi gói); chuyển đổi tùy chỉnh (hoàn thành mục tiêu, bước phễu). Thư viện sự kiện theo loại hình: [references/event-library.md](references/event-library.md) (tiếng Anh).

## Quy ước đặt tên

Dạng **đối_tượng_hành_động**, chữ thường, gạch dưới, **tiếng Anh không dấu** (công cụ và đội kỹ thuật dùng chung): `signup_completed`, `form_submitted`, `checkout_payment_completed`, `zalo_clicked`, `phone_clicked`.
- Cụ thể: `cta_hero_clicked` hơn `button_clicked`; bối cảnh để trong thuộc tính, không nhồi vào tên
- Không khoảng trắng, ký tự đặc biệt, dấu tiếng Việt
- **Giữ tên do nhà cung cấp định nghĩa** khi dùng sự kiện tự động/khuyến nghị (GA4 `click`, `view_search_results`, `purchase`, `generate_lead`). Ánh xạ tên nội bộ sang tên đó rõ ràng; tự đặt tên sự kiện không làm công cụ tự thu nó.

## Sự kiện thiết yếu

**Website marketing/bán hàng**

| Sự kiện | Thuộc tính |
|---|---|
| `cta_clicked` | button_text, location |
| `form_submitted` / GA4 `generate_lead` | form_type |
| `phone_clicked` | location (bấm link `tel:`) |
| `zalo_clicked`, `messenger_clicked` | location (bấm nút chat) |
| `signup_completed` / GA4 `sign_up` | method, source |
| `demo_requested`, `booking_completed` | service |

**Thương mại điện tử:** chuỗi khuyến nghị của GA4 — `view_item`, `add_to_cart`, `begin_checkout`, `add_payment_info` (payment_type: cod, bank_transfer, ewallet, card), `purchase` (transaction_id, value, currency `VND`). Trạng thái giao/hoàn đơn COD đưa vào từ hệ thống quản lý đơn (gửi sự kiện phía máy chủ hoặc nhập dữ liệu), không đoán từ website.

**Sản phẩm/ứng dụng:** `onboarding_step_completed` (step_number, step_name), `feature_used` (feature_name), `purchase_completed` (plan, value), `subscription_cancelled` (reason).

## Thuộc tính sự kiện

| Nhóm | Thuộc tính |
|---|---|
| Trang | page_title, page_location, page_referrer |
| Người dùng | user_id (mã nội bộ, không phải số điện thoại), user_type, account_id, plan_type |
| Chiến dịch | source, medium, campaign, content, term |
| Sản phẩm | item_id, item_name, item_category, price |

Tên thuộc tính nhất quán; không trùng thuộc tính tự động; **không đưa thông tin cá nhân** (tên, số điện thoại, email, địa chỉ) vào thuộc tính.

## GA4

Thiết lập nhanh: tạo property + luồng dữ liệu → cài gtag.js hoặc GTM → bật đo lường nâng cao → cấu hình sự kiện tùy chỉnh → đánh dấu sự kiện chính (key event) trong Admin. Tiền tệ báo cáo đặt VND, múi giờ GMT+7.

```javascript
// Sự kiện khuyến nghị sign_up của GA4 để vào báo cáo có sẵn.
// Kế hoạch đo có thể gọi là signup_completed; ánh xạ rõ ràng.
gtag('event', 'sign_up', { method: 'zalo', plan: 'free' });
// Bấm nút Zalo
gtag('event', 'zalo_clicked', { location: 'floating_button' });
```
Chi tiết: [references/ga4-implementation.md](references/ga4-implementation.md).

## Google Tag Manager

Thẻ (mã chạy: GA4, pixel), trình kích hoạt (khi nào chạy), biến (giá trị động).
```javascript
dataLayer.push({ event: 'form_submitted', form_name: 'bao_gia', form_location: 'footer' });
```
Bấm gọi/Zalo: trình kích hoạt "Click – Just Links" với điều kiện Click URL bắt đầu bằng `tel:` hoặc chứa `zalo.me`, `m.me`. Chi tiết: [references/gtm-implementation.md](references/gtm-implementation.md).

---

## Chiến lược UTM

| Tham số | Mục đích | Ví dụ |
|---|---|---|
| utm_source | Nguồn | facebook, zalo, tiktok, google, coccoc, newsletter |
| utm_medium | Phương tiện | cpc, paid-social, email, zalo-oa, zns, sms, social |
| utm_campaign | Chiến dịch | sale-11-11, tet-2027 |
| utm_content | Phân biệt phiên bản | video-review-a, banner-top |
| utm_term | Từ khóa tìm kiếm trả phí | giay-chay-bo |

- **Chữ thường toàn bộ** — GA4 coi `Facebook` và `facebook` là hai nguồn, không gộp lại được
- **Gạch nối giữa các từ**, không dấu tiếng Việt, không khoảng trắng; một quy ước cho cả công ty
- **Một cách viết cho mỗi nguồn** — luôn `facebook`, không lúc `fb` lúc `facebook.com`; giữ danh sách giá trị cho phép trong một bảng dùng chung
- **Không dữ liệu cá nhân** trong UTM — không email, tên, số điện thoại, mã khách
- **Cụ thể nhưng ngắn**
- **Thử link cuối cùng** — rút gọn link, chuyển hướng, trình duyệt trong app Facebook/Zalo có thể làm rơi tham số

**Theo loại đối tác** (`utm_medium` = loại thỏa thuận, `utm_source` = ai gửi traffic):

| Loại | utm_source | utm_medium | utm_campaign | utm_content |
|---|---|---|---|---|
| Bản tin | `{doi-tac}` | `newsletter` | `{doi-tac}-{an-pham}-{yyyy}-{mm}` | `{vi-tri}-{yyyy-mm-dd}` |
| KOL/KOC | `{nen-tang}` | `creator` | `{ten-nha-sang-tao}` | ngày đăng hoặc mã video |
| Podcast | `{podcast}` | `podcast` | `{podcast}-{yyyy}-{mm}` | `{vi-tri}-{yyyy-mm-dd}` |
| Affiliate/CTV | `{doi-tac}` | `affiliate` | `{doi-tac}-affiliate` | vị trí |
| Cộng đồng | `{cong-dong}` | `community` | `{cong-dong}-{chuong-trinh}` | kênh/bài |
| Tin Zalo OA/ZNS | `zalo` | `zalo-oa` hoặc `zns` | `{chien-dich}` | `{mau-tin}` |

- `creator` cho hợp tác nhà sáng tạo trả phí, không dùng `social` (lẫn với bài tự nhiên)
- Mỗi vị trí một link
- **Tạo nhóm kênh tùy chỉnh trong GA4** — nhóm mặc định đẩy `newsletter`, `creator`, `podcast`, `community`, `zalo-oa` vào "Unassigned"
- Video/livestream/podcast không bấm link được → kèm mã giảm giá riêng hoặc link ngắn dễ nhớ (xem `influencer-marketing`)

## Traffic từ trợ lý AI

Không gắn UTM được cho link ChatGPT, Claude, Gemini, Perplexity, Copilot đưa vào câu trả lời. Một số lượt có referrer (`chatgpt.com`, `perplexity.ai`), nhiều lượt thành "direct" hoặc quay lại qua tìm kiếm thương hiệu. Tạo quy tắc nhóm kênh "Trợ lý AI" theo referrer đã biết, cập nhật danh sách; coi đó là **mức sàn**. Đo đầy đủ: `ai-seo`; đối chiếu: `attribution`.

---

## Gỡ lỗi và kiểm tra

Công cụ: GA4 DebugView, chế độ Preview của GTM, Tag Assistant, tiện ích xem dataLayer.

- [ ] Sự kiện chạy đúng lúc
- [ ] Giá trị thuộc tính đúng (giá trị đơn tính bằng VND, không lệch 1.000 lần)
- [ ] Không trùng sự kiện (nhiều container, trình kích hoạt chạy hai lần)
- [ ] Chạy trên nhiều trình duyệt, điện thoại, **trình duyệt trong app Facebook/Zalo/TikTok**
- [ ] Chuyển đổi ghi đúng
- [ ] Không rò rỉ thông tin cá nhân

| Lỗi | Kiểm tra |
|---|---|
| Sự kiện không chạy | Cấu hình trình kích hoạt, GTM đã tải |
| Giá trị sai | Đường dẫn biến, cấu trúc dataLayer, định dạng số |
| Trùng sự kiện | Nhiều container, trình kích hoạt chạy hai lần |

## Quyền riêng tư và tuân thủ

- **Luật Bảo vệ dữ liệu cá nhân 2025:** công cụ đo, pixel, cookie định danh người dùng là xử lý dữ liệu cá nhân — thông báo rõ trong chính sách quyền riêng tư và cân nhắc cơ chế xin đồng ý trước khi kích hoạt các thẻ không thiết yếu; hỏi luật sư về mức yêu cầu cụ thể cho website của người dùng ([vn-legal.md](references/vn/vn-legal.md), mục 5).
- Khách ở EU/UK/Canada: bắt buộc banner đồng ý; dùng Consent Mode (chờ đồng ý).
- Không đưa thông tin cá nhân vào thuộc tính/UTM; đặt thời gian lưu dữ liệu; có khả năng xóa dữ liệu người dùng; chỉ thu cái cần.

## Đầu ra: tài liệu kế hoạch đo lường

```markdown
# Kế hoạch đo lường — [Website/Sản phẩm]
## Tổng quan
- Công cụ: GA4, GTM | Cập nhật: [ngày]
## Sự kiện
| Tên | Mô tả | Thuộc tính | Kích hoạt |
| zalo_clicked | Bấm nút chat Zalo | location | Bấm link zalo.me |
## Chiều tùy chỉnh
| Tên | Phạm vi | Tham số |
## Chuyển đổi (key events)
| Chuyển đổi | Sự kiện | Cách đếm |
```

Với phân tích số liệu (xuất từ GA4, quảng cáo, sàn, đơn hàng): đưa dữ liệu vào tệp, tính bằng code, trình bày bảng/biểu đồ. Đọc dữ liệu qua kết nối (GA4 MCP…) nếu phiên có; không có thì nhờ người dùng xuất CSV.

## Công cụ

GA4 (có MCP), Mixpanel, Amplitude, PostHog, Segment — hướng dẫn trong [danh mục công cụ](https://github.com/coreyhaines31/marketingskills/blob/main/tools/REGISTRY.md). Bản đồ nhiệt/ghi phiên: Microsoft Clarity (miễn phí), Hotjar.

## Skill liên quan

- `conversion-tracking` — gửi chuyển đổi về nền tảng quảng cáo và GA4, kiểm tra đã tới
- `attribution` — mô hình quy công, đối chiếu số liệu lệch giữa các công cụ
- `ab-testing` — đo thử nghiệm
- `cro` — dùng dữ liệu để tối ưu chuyển đổi
- `marketplaces` — số liệu trên sàn
- `revops` — chỉ số pipeline, CRM
