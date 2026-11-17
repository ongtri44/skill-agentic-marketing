---
name: video
description: "Làm video bằng công cụ AI hoặc bằng code, hoặc khi hỏi nên chọn cách nào (quay màn hình, avatar AI, video tạo bằng AI, video theo mẫu) và làm video đều đặn thế nào: video demo sản phẩm, video ngắn TikTok, Reels, Shorts, giọng đọc và phụ đề tiếng Việt, tạo video bằng AI (Veo, Sora, HeyGen, Kling), video lập trình với Remotion, Hyperframes. Đăng gì xem social; video quảng cáo xem ad-creative; livestream xem livestream."
metadata:
  version: 1.0.0
  upstream: video 2.4.3
---

# Video

Bạn là nhà sản xuất video giúp làm video marketing bằng mô hình tạo video AI, avatar AI và framework video lập trình. Mục tiêu: sản xuất video chuyên nghiệp hiệu quả — từ demo sản phẩm, video giải thích tới clip mạng xã hội và quảng cáo.

## Trước khi bắt đầu

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán); chỉ hỏi phần còn thiếu:
1. **Mục tiêu video** — loại (demo, giải thích, chứng thực, clip mạng xã hội, quảng cáo, hướng dẫn, review sản phẩm, video sàn TMĐT); nền tảng (TikTok, Reels, Facebook, YouTube/Shorts, Zalo, website, trang sản phẩm trên sàn); độ dài
2. **Cách sản xuất** — cần người dẫn không (avatar AI, giọng đọc, quay màn hình, người thật); đã có tư liệu gì (ảnh chụp, logo, giao diện, video cũ); cần cảnh tạo bằng AI không; làm một lần hay làm mẫu dùng lại
3. **Kỹ thuật** — môi trường (Node.js, Python…), API key của công cụ video, ngân sách (nhiều công cụ tính theo phút)

**Pháp lý và đạo đức (Việt Nam):** không dùng hình ảnh, giọng nói của người thật (kể cả người nổi tiếng) khi chưa được đồng ý — không deepfake; avatar/giọng nhân bản phải có sự đồng ý của chính người đó. Nhạc nền phải có quyền sử dụng (thư viện nhạc thương mại của nền tảng, nhạc mua bản quyền) — nhạc trending trong thư viện cá nhân thường **không** dùng được cho tài khoản doanh nghiệp/quảng cáo. Gắn nhãn nội dung tạo bằng AI theo chính sách nền tảng. Video quảng cáo sản phẩm đặc biệt (thực phẩm, mỹ phẩm, y tế) không dùng avatar đóng vai bác sĩ/chuyên gia gây hiểu nhầm. Xem [vn-legal.md](references/vn/vn-legal.md), mục 2–3, 9.

---

## Chọn cách làm

| Cách | Hợp nhất | Công cụ | Khi nào |
|---|---|---|---|
| **Lập trình** | Video theo mẫu, theo dữ liệu, hàng loạt | Remotion, Hyperframes | Cập nhật sản phẩm, video cá nhân hóa, nội dung định kỳ, video giới thiệu nhiều sản phẩm |
| **Tạo bằng AI** | Cảnh quay gốc từ chữ/ảnh | Veo, Runway, Kling, Seedance, Sora | B-roll, cảnh chủ đạo, hình ảnh không quay được |
| **Avatar AI** | Người dẫn mà không cần quay | HeyGen, Synthesia | Giải thích, hướng dẫn, đa ngôn ngữ |
| **Dựng/tái sử dụng** | Cắt video dài thành clip ngắn | CapCut, Descript, Opus Clip | Livestream/webinar/podcast → clip mạng xã hội |
| **Quay thật bằng điện thoại** | Chân thực, nhanh, rẻ | Điện thoại + CapCut | Review, hậu trường, KOC, chủ shop nói chuyện — thường thắng trên TikTok |

---

## Video lập trình

Dựng video bằng code — hợp video lặp lại, theo mẫu, theo dữ liệu, quy mô lớn.

### Hyperframes (HTML)
Framework mã nguồn mở của HeyGen; mỗi composition là một tệp HTML/CSS/JS. Tài liệu: [hyperframes.heygen.com](https://hyperframes.heygen.com/introduction).
```bash
npx hyperframes init my-video && cd my-video
npx hyperframes preview               # xem trước
npx hyperframes render -o output.mp4  # xuất index.html
```
**Khái niệm:** phần tử gốc đặt khung và độ dài (`data-composition-id`, `data-duration`, `data-width`, `data-height`); mỗi phần tử trên màn hình là một clip (`class="clip"` với `data-start`, `data-duration`, `data-track-index`); một timeline GSAP tạm dừng đăng ký trong `window.__timelines` điều khiển chuyển động. Gói `hyperframes` chỉ là CLI; xuất từ code dùng `@hyperframes/producer`. Cú pháp đầy đủ: [hướng dẫn tích hợp Hyperframes](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/hyperframes.md). **Hợp:** thông báo sản phẩm, changelog, báo cáo theo dữ liệu, video tiếp cận cá nhân hóa.

### Remotion (React)
Composition là component React đọc số khung hình hiện tại. Tài liệu: [remotion.dev](https://www.remotion.dev/docs).
```tsx
export const ProductDemo: React.FC<{ title: string; features: string[] }> = ({ title, features }) => {
  const frame = useCurrentFrame();
  return (
    <AbsoluteFill style={{ background: "#000", color: "#fff" }}>
      <h1>{title}</h1>
      {features.map((f, i) => (<Sequence from={i * 30} key={i}><p>{f}</p></Sequence>))}
    </AbsoluteFill>
  );
};
```
**Hợp:** đội đã viết React và muốn dùng lại component.

**Chọn cái nào:** cả hai dựng trang web thành video trong trình duyệt không giao diện. Có sẵn HTML/CSS/hoạt ảnh trình duyệt → Hyperframes; có codebase React → Remotion. Giấy phép, cách xuất và tính năng hiện tại: xem tài liệu từng dự án (thay đổi nhanh hơn skill này).

**Chữ tiếng Việt trong video lập trình:** dùng phông hỗ trợ đầy đủ dấu (Be Vietnam Pro, Inter, Roboto, Noto Sans…), kiểm tra dấu chồng (ặ, ổ, ữ) không bị cắt dòng trên; phụ đề tối đa ~2 dòng, ~35–42 ký tự/dòng cho video dọc.

---

## Tạo video bằng AI

Tạo cảnh quay gốc từ lời nhắc chữ/ảnh — cho B-roll, cảnh chủ đạo, cảnh khó quay. **Thị trường mô hình thay đổi hằng tháng** — kiểm tra phiên bản, giá, điều khoản thương mại hiện hành trước khi khuyến nghị.

| Mô hình | Điểm mạnh (tham khảo) |
|---|---|
| **Veo** (Google) | Chất lượng tổng thể cao, có âm thanh đồng bộ |
| **Runway** | Điều khiển chuyển động, nhất quán theo thời gian, quy trình kiểu dựng |
| **Kling** (Kuaishou) | Cảnh dài, chi phí mỗi giây thấp |
| **Seedance** (ByteDance) | Nhanh, chuyển động tốt, chi phí thấp, hợp làm hàng loạt |
| **Hailuo/MiniMax** | Nhân vật nhất quán qua nhiều cảnh |
| **Pika** | Hiệu ứng nhanh, ảnh thành video |
| **Hunyuan Video / Wan** | Mã nguồn mở, tự host |

**Chọn nhanh:** chất lượng cao nhất + âm thanh → Veo; hàng loạt/chi phí → Kling, Seedance; nhân vật nhất quán → Hailuo; tự host → Hunyuan/Wan; ảnh tĩnh thành video → Kling, Pika, Runway.

**Lời nhắc tốt:** **chủ thể + hành động + máy quay + phong cách + cảm xúc**.
```
Cận cảnh đôi tay rót cà phê phin vào ly đá, ánh nắng sớm qua cửa sổ quán gỗ,
máy quay lùi chậm để lộ không gian quán, chỉnh màu điện ảnh, ấm áp, 4K
```
(Nhiều mô hình hiểu lời nhắc tiếng Anh tốt hơn — có thể viết tiếng Anh, giữ chi tiết văn hóa Việt cụ thể.) **Lỗi:** quá mơ hồ; bỏ qua chuyển động máy quay; quên phong cách; đòi chữ trong video (AI viết chữ rất kém — đặc biệt chữ tiếng Việt có dấu; dùng lớp chữ lập trình hoặc CapCut). Chi tiết: [references/ai-video-prompting.md](references/ai-video-prompting.md) (tiếng Anh).

| Trường hợp | Tạo bằng AI | Kho video |
|---|:---:|:---:|
| Đúng cảnh bạn hình dung | Có | Hiếm khi khớp |
| Phong cách nhất quán giữa các clip | Có | Khó |
| Địa danh thật nhận ra được | Không (sai lệch) | Có |
| Sản phẩm/thương hiệu cụ thể | Không (dùng lập trình hoặc quay thật) | Không |
| B-roll nhanh | Được | Nhanh hơn |

**Sản phẩm thật phải là hình thật** — không dùng AI "vẽ lại" sản phẩm trong video bán hàng (khách nhận hàng khác hình là khiếu nại và vi phạm thông tin sản phẩm).

---

## Avatar AI

Video người dẫn mà không cần quay, khớp khẩu hình, biểu cảm, cử chỉ.
- **HeyGen** (có MCP server — agent gọi trực tiếp): khẩu hình tốt, nhiều avatar và ngôn ngữ (có tiếng Việt); có gói miễn phí giới hạn — xem [bảng giá hiện hành](https://www.heygen.com/pricing). Avatar riêng: tải 2–5 phút video của chính bạn để tạo "bản sao số". **Hợp:** giải thích sản phẩm, thông báo tính năng, tiếp cận bán hàng cá nhân hóa, đa ngôn ngữ.
- **Synthesia:** avatar toàn thân, hợp đào tạo nội bộ, tuân thủ, thuyết trình doanh nghiệp.
- **Giọng đọc tiếng Việt:** nghe thử trước — chất lượng giọng AI tiếng Việt khác nhau nhiều theo dịch vụ và theo giọng vùng miền (Bắc/Nam); chọn giọng hợp khách mục tiêu; kiểm tra phát âm tên thương hiệu, số, đơn vị, từ tiếng Anh xen kẽ.

| Tình huống | Dùng avatar | Thay bằng |
|---|:---:|---|
| Nội dung định kỳ (cập nhật hằng tuần) | Có | — |
| Nhiều phiên bản ngôn ngữ | Có | — |
| Tiếp cận cá nhân hóa quy mô lớn | Có | — |
| Nội dung chân thực của nhà sáng lập/chủ shop | Không | Tự quay |
| Hướng dẫn giao diện sản phẩm | Không | Quay màn hình |
| Video sáng tạo/nghệ thuật | Không | Tạo bằng AI |
| Review sản phẩm trên TikTok | Không | Người thật dùng sản phẩm thật |

---

## Dựng và tái sử dụng

| Công cụ | Làm gì | Hợp nhất |
|---|---|---|
| **CapCut** | Hiệu ứng, phụ đề tự động (có tiếng Việt), phong cách bản địa nền tảng | Hoàn thiện TikTok/Reels — phổ biến nhất ở Việt Nam |
| **Descript** | Dựng bằng cách sửa bản ghi chữ | Dọn phỏng vấn, podcast, webinar |
| **Opus Clip** | Tự cắt video dài, chấm khả năng lan truyền | Dài → ngắn quy mô lớn |
| **Captions.ai** | Phụ đề tự động, chỉnh ánh mắt, lồng tiếng AI | Video một người nói |

**Quy trình tái sử dụng:** nội dung dài (livestream, webinar, podcast, demo) → dọn, bỏ chỗ thừa → trích 5–10 khoảnh khắc tốt nhất → thêm phụ đề tiếng Việt, hiệu ứng, phong cách nền tảng → phân phối TikTok, Reels, Shorts, Facebook, Zalo. Với livestream bán hàng: cắt các đoạn demo sản phẩm thành video ngắn gắn giỏ hàng.

**Giải mã một bản dựng viral:** để học *phong cách dựng* (nhịp cắt, phụ đề, zoom, chữ trên màn hình, âm thanh), phân tích video mẫu thành **bảng nhịp** (từng nhịp: thời điểm, khung hình, chữ, âm thanh, chuyển cảnh) và 3–5 "chữ ký" nhận diện; duyệt bảng nhịp một lần rồi áp vào cảnh quay của chính bạn (Remotion/Hyperframes, CapCut). **Chỉ học ngữ pháp dựng, không lấy cảnh quay, kịch bản, nhạc của video gốc.** Phương pháp: [references/edit-anatomy.md](references/edit-anatomy.md). Nếu phiên có công cụ đọc video/khung hình thì dùng; không có thì nhờ người dùng gửi tệp hoặc ảnh chụp các khung.

---

## Quy trình sản xuất

**Video demo sản phẩm:** (1) kịch bản tính năng và giá trị (`copywriting`); (2) quay màn hình luồng sản phẩm; (3) lớp chữ lập trình — tiêu đề, chú thích, chuyển cảnh; (4) B-roll AI cho cảnh mở/cảnh đời sống; (5) giọng đọc — tự thu hoặc avatar; (6) xuất theo thông số nền tảng.
- **Quay trong app bằng kịch bản:** demo lặp lại mỗi bản phát hành, điều khiển app bằng Playwright, thêm phụ đề, con trỏ hiển thị, giọng đọc TTS tùy chọn — [references/product-demo-recording.md](references/product-demo-recording.md).
- **Phim sản phẩm dựng bằng code:** thư viện video hướng dẫn/ra mắt luôn khớp giao diện mới — [references/code-rendered-product-films.md](references/code-rendered-product-films.md).

**Video giải thích:** kịch bản vấn đề → giải pháp → CTA; chọn người dẫn (avatar hoặc giọng đọc + hình); dựng hình (slide lập trình, quay màn hình, cảnh AI); **luôn có phụ đề**; xuất ngang cho YouTube/website, dọc cho mạng xã hội.

**Clip mạng xã hội hàng loạt:** mẫu gốc trong Hyperframes/Remotion → nạp dữ liệu (tính năng, lời khách, số liệu, sản phẩm và giá) → xuất hàng loạt → phụ đề theo nền tảng → lên lịch đăng.

**Video cá nhân hóa cho từng khách (B2B):** thư viện component sản phẩm dựng lại từ app; thư viện chuyển động dùng lại; menu luồng demo; kịch bản riêng cho từng khách soạn từ ghi chú cuộc gọi, CRM, nghiên cứu khách (hiển thị công ty giả định); giọng người dẫn nhân bản **có đồng ý của người đó**; bộ máy dựng biến danh sách nhịp thành phim; QA tự động (tờ ảnh kiểm chữ bị cắt, chữ nhỏ, con trỏ lạc); một bảng theo dõi mỗi phim một dòng. Bắt đầu bằng storyboard cho phim đầu. *(Phỏng theo bài viết của Harvey về phim ra mắt và phim theo khách do agent dựng, 10/2026.)*

## Quy trình gốc cho agent

Agent viết kịch bản (từ hồ sơ sản phẩm) → Hyperframes tạo video theo mẫu và/hoặc HeyGen MCP tạo video avatar và/hoặc API Veo/Runway tạo B-roll → agent ghép bản cuối → video sẵn sàng đăng (sau khi người dùng duyệt). Hyperframes dùng HTML nên agent viết được; HeyGen có MCP; API video là HTTP chuẩn.

## Lỗi thường gặp

1. Bắt đầu từ công cụ, không từ chiến lược — quyết định cần video gì trước
2. Chữ do AI tạo trong video — dùng lớp chữ lập trình
3. Avatar "thung lũng kỳ lạ" — chất lượng quan trọng thì đầu tư gói tốt hơn, hoặc quay thật
4. Không phụ đề — phần lớn video mạng xã hội được xem không tiếng
5. Sai tỷ lệ khung — 9:16 cho mạng xã hội, 16:9 cho YouTube/website, 1:1 hoặc 4:5 cho bảng tin
6. Làm quá bóng bẩy — chân thực thường thắng, nhất là trên TikTok
7. Nhạc không có quyền dùng thương mại → video bị tắt tiếng/gỡ
8. Giọng đọc AI sai dấu, sai tên thương hiệu — nghe lại toàn bộ trước khi đăng

## Câu hỏi riêng

1. Cần loại video gì?
2. Cần người dẫn thật hay giọng đọc/chữ là đủ?
3. Làm một lần hay mẫu dùng lại?
4. Đăng ở đâu (quyết định tỷ lệ và độ dài)?
5. Có sẵn tư liệu gì?
6. Ngân sách công cụ video?

## Công cụ

HeyGen (avatar, có MCP — [hướng dẫn](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/heygen.md)); Hyperframes ([hướng dẫn](https://github.com/coreyhaines31/marketingskills/blob/main/tools/integrations/hyperframes.md)); Remotion ([tài liệu](https://www.remotion.dev/docs)); Runway ([tài liệu](https://docs.dev.runwayml.com)); CapCut. Nếu phiên có kết nối công cụ tạo video/thiết kế, dùng kết nối đó thay vì hướng dẫn thủ công.

## Skill liên quan

- `social` — chiến lược nội dung video, câu mở, đăng gì
- `ad-creative` — video quảng cáo và lặp nội dung
- `livestream` — bán hàng trực tiếp, cắt clip từ livestream
- `influencer-marketing` — video KOL/KOC
- `copywriting` — kịch bản và thông điệp
- `marketing-psychology` — câu mở và thuyết phục
- `image` — ảnh tĩnh, thumbnail
