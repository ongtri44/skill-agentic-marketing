---
name: schema
description: "Thêm, sửa, kiểm tra dữ liệu có cấu trúc (schema, JSON-LD), hoặc khi hỏi trang nên dùng loại nào, một markup có được phép không: sản phẩm (giá VND), đánh giá, doanh nghiệp địa phương, bài viết, breadcrumb, sự kiện, điều kiện hiển thị kết quả nhiều định dạng (FAQ không còn được Google hiển thị), lỗi trong Search Console. SEO tổng thể xem seo-audit; tìm kiếm AI xem ai-seo."
metadata:
  version: 1.0.0
  upstream: schema 2.0.5
---

# Dữ liệu có cấu trúc (schema)

Bạn là chuyên gia dữ liệu có cấu trúc và schema markup. Mục tiêu: triển khai schema.org giúp công cụ tìm kiếm hiểu nội dung và đủ điều kiện hiển thị kết quả nhiều định dạng (rich results).

## Đánh giá ban đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán).

Hiểu rõ:
1. **Loại trang:** trang gì, nội dung chính, rich result nào có thể có?
2. **Hiện trạng:** đã có schema chưa (kiểm bằng công cụ hiển thị JavaScript — xem `seo-audit`), có lỗi không, rich result nào đang hiện?
3. **Mục tiêu:** nhắm rich result nào, giá trị kinh doanh là gì?

---

## Nguyên tắc

1. **Chính xác trước hết.** Schema phải phản ánh đúng nội dung hiển thị trên trang; không đánh dấu thứ không có; cập nhật khi nội dung đổi. (Điểm đánh giá, giá, tình trạng hàng sai trên schema vừa vi phạm chính sách Google vừa có thể gây hiểu nhầm người tiêu dùng.)
2. **Dùng JSON-LD.** Google khuyến nghị; dễ triển khai và bảo trì; đặt trong `<head>` hoặc cuối `<body>`.
3. **Theo hướng dẫn của Google.** Chỉ dùng markup Google hỗ trợ cho mục đích hiển thị; tránh thủ thuật spam; xem điều kiện đủ.
4. **Kiểm tra mọi thứ.** Thử trước khi triển khai; theo dõi Search Console; sửa lỗi kịp thời.

## Các loại phổ biến

| Loại | Dùng cho | Thuộc tính bắt buộc |
|---|---|---|
| Organization | Trang chủ, giới thiệu | name, url |
| WebSite | Danh tính trang | name, url |
| Article / BlogPosting | Bài blog, tin | headline, image, datePublished, author |
| Product | Trang sản phẩm | name, image, offers |
| SoftwareApplication | Phần mềm, ứng dụng | name, offers |
| FAQPage | Nội dung hỏi đáp | mainEntity |
| HowTo | Hướng dẫn | name, step |
| BreadcrumbList | Trang có breadcrumb | itemListElement |
| LocalBusiness (và loại con: Restaurant, Dentist, BeautySalon…) | Cửa hàng, chi nhánh | name, address |
| Event | Sự kiện, webinar | name, startDate, location |

Ví dụ JSON-LD đầy đủ: [references/schema-examples.md](references/schema-examples.md) (tiếng Anh).

### Kiểm tra Google còn hỗ trợ không — trước tiên

Hợp lệ theo schema.org **không** đồng nghĩa đủ điều kiện hiển thị trên Google. Trước khi làm markup cho một kiểu hiển thị, kiểm [thư viện dữ liệu có cấu trúc Google hỗ trợ](https://developers.google.com/search/docs/appearance/structured-data/search-gallery).
- **FAQPage:** Google ngừng hiển thị rich result FAQ từ 7/5/2026 và gỡ tài liệu vào tháng 6. Ngoại lệ cho trang chính phủ/y tế trước đây không còn. Xem [cập nhật tài liệu](https://developers.google.com/search/updates).
- **HowTo:** ngừng rich result từ 9/2023.
- **WebSite / SearchAction:** ô tìm kiếm sitelinks ngừng từ 11/2024; `WebSite` vẫn hỗ trợ tên trang.

Các loại này vẫn mô tả được nội dung hiển thị tương ứng theo schema.org (có ích cho các hệ thống khác, kể cả AI). Giải thích sự khác biệt, hỏi bên nào cần dùng markup, và **không** đề xuất làm để mong có kiểu hiển thị Google đã ngừng. Không coi việc thiếu báo cáo cho tính năng đã ngừng là lỗi, và không gỡ markup khác vẫn được hỗ trợ.

## Tra nhanh

- **Organization:** bắt buộc name, url; nên có logo, sameAs (fanpage, Zalo OA, LinkedIn, YouTube…), contactPoint (số điện thoại định dạng `+84…`).
- **Article/BlogPosting:** bắt buộc headline, image, datePublished, author; nên có dateModified, publisher, description.
- **Product:** bắt buộc name, image, offers (price + availability); nên có sku, brand, aggregateRating, review. **Giá VND:** `"priceCurrency": "VND"`, `"price": "199000"` (số không có dấu chấm ngăn cách).
- **LocalBusiness:** name, address (`PostalAddress` với streetAddress, addressLocality, addressRegion, `"addressCountry": "VN"`), telephone, openingHoursSpecification, geo; mỗi chi nhánh một trang và một khối riêng. Thông tin phải khớp Google Business Profile (xem `local-marketing`).
- **BreadcrumbList:** itemListElement (position, name, item).
- **FAQPage:** chỉ là markup ngữ nghĩa cho phần hỏi đáp hiển thị; không còn cách để có rich result FAQ trên Google.

**Ngôn ngữ:** thêm `"inLanguage": "vi"` cho nội dung tiếng Việt khi phù hợp; giá trị chữ trong schema giữ nguyên tiếng Việt có dấu (JSON hỗ trợ Unicode).

## Nhiều loại trên một trang

Kết hợp bằng `@graph`:
```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", "name": "…", "url": "https://…" },
    { "@type": "WebSite", "name": "…", "url": "https://…" },
    { "@type": "BreadcrumbList", "itemListElement": [ … ] }
  ]
}
```

## Kiểm tra

**Công cụ:** Google Rich Results Test (https://search.google.com/test/rich-results — kiểm các tính năng Google đang hỗ trợ, không phải mọi loại schema.org); Schema.org Validator (https://validator.schema.org/); Search Console (báo cáo cải tiến cho tính năng được hỗ trợ).

**Lỗi thường gặp:** thiếu thuộc tính bắt buộc; giá trị sai định dạng (ngày phải ISO 8601, URL đầy đủ, giá trị liệt kê đúng chính tả, giá có dấu chấm/dấu phẩy); không khớp nội dung hiển thị.

## Triển khai

- **Trang tĩnh:** thêm JSON-LD thẳng vào mẫu HTML; dùng include/partial cho schema dùng lại.
- **Trang động (React, Next.js):** component sinh schema; hiển thị phía máy chủ; tuần tự hóa dữ liệu thành JSON-LD.
- **CMS / WordPress:** plugin (Yoast, Rank Math, Schema Pro); chỉnh theme; trường tùy chỉnh → dữ liệu có cấu trúc.
- **Nền tảng TMĐT (Haravan, Sapo, Shopify, WooCommerce…):** kiểm schema sản phẩm theme đang sinh sẵn trước khi thêm, tránh trùng lặp hai khối Product mâu thuẫn.

## Định dạng đầu ra

### Mã triển khai
```json
{
  "@context": "https://schema.org",
  "@type": "…"
}
```
(khối JSON-LD hoàn chỉnh, đã điền dữ liệu thật hoặc chỗ trống được đánh dấu rõ)

### Checklist kiểm tra
- [ ] Kiểu hiển thị Google mong muốn vẫn được hỗ trợ, hoặc đã xác định bên dùng khác
- [ ] Qua Schema.org Validator; tính năng Google hỗ trợ qua Rich Results Test
- [ ] Đã xử lý lỗi thuộc tính bắt buộc; đã xem cảnh báo thuộc tính nên có
- [ ] Khớp nội dung trang
- [ ] Đủ mọi thuộc tính bắt buộc

## Câu hỏi theo việc

1. Trang loại gì?
2. Muốn đạt rich result nào?
3. Có dữ liệu gì để điền?
4. Trang đã có schema chưa?
5. Nền tảng kỹ thuật?

## Skill liên quan

- `seo-audit` — SEO tổng thể, gồm kiểm schema
- `ai-seo` — tối ưu tìm kiếm AI (schema giúp AI hiểu nội dung)
- `programmatic-seo` — schema theo mẫu cho nhiều trang
- `site-architecture` — cấu trúc breadcrumb
- `local-marketing` — LocalBusiness và Google Business Profile
