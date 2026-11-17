---
name: marketing-loops
description: "Thiết lập việc marketing định kỳ để AI chạy theo lịch hoặc theo sự kiện kích hoạt, hoặc khi hỏi một lần kiểm tra hằng tuần, hằng ngày nên làm gì, nhớ gì, khi nào dừng: kiểm tra SEO, quảng cáo mỏi, theo dõi khách sắp rời, phân loại phản hồi outbound, báo cáo tuần, theo dõi đánh giá và giá trên sàn. Ý tưởng làm một lần xem marketing-ideas; vòng thử nghiệm xem ab-testing."
metadata:
  version: 1.0.0
  upstream: marketing-loops 1.8.4
---

# Vòng lặp marketing

Bạn giúp thiết lập **vòng lặp marketing** — quy trình lặp lại mà AI chạy theo nhịp, mỗi vòng có kích hoạt rõ, tập bước giới hạn, tự kiểm tra, và điều kiện dừng rõ ràng. Vòng lặp biến việc bạn thường làm tay (rồi quên) thành hệ thống luôn chạy: quét cơ hội SEO hằng tuần, làm mới quảng cáo bị mỏi, theo dõi tín hiệu khách sắp rời, theo dõi đánh giá và giá đối thủ trên sàn.

Đây là "người anh em vận hành" của `marketing-ideas`: ý tưởng cho biết *thử gì một lần*; vòng lặp cho biết *tiếp tục làm gì theo lịch* — và nối các skill marketing khác lại để làm việc đó.

## Cách dùng

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán); chỉ hỏi phần còn thiếu. Rồi:
1. **Làm rõ việc:** vòng lặp bảo vệ hay tăng kết quả nào (thứ hạng, hiệu quả quảng cáo, kích hoạt, giữ chân, doanh thu, giới thiệu, điểm đánh giá shop)?
2. **Chọn vòng lặp** trong [references/loop-catalog.md](references/loop-catalog.md) (tiếng Anh, 60 vòng) — hoặc điều chỉnh vòng gần nhất.
3. **Chỉnh nhịp** theo tốc độ thay đổi thật của tín hiệu (luật nhịp bên dưới).
4. **Xác nhận điểm duyệt của người:** việc gì tự làm, việc gì chuẩn bị sẵn chờ duyệt trước khi đăng hoặc chi tiền — [references/loop-guardrails.md](references/loop-guardrails.md).
5. **Lên lịch** (xem bên dưới).

Nhiều vòng lặp hoặc cả một hệ điều hành marketing: [references/loop-orchestration.md](references/loop-orchestration.md) — cách ghép và thứ tự áp dụng (bắt đầu bằng đo lường + báo cáo tuần; đừng dựng tất cả cùng lúc).

## Giải phẫu một vòng lặp

Mỗi vòng phải đủ chín phần — thiếu điều kiện dừng, tự kiểm tra hoặc xử lý trạng thái là một khoản nợ, không phải tài sản.

| Phần | Định nghĩa |
|---|---|
| **Nhịp kiểm tra** | Bao lâu *nhìn* một lần (tuần/ngày/khi kích hoạt) — khớp tốc độ tín hiệu |
| **Hành động khi** | Điều kiện để thật sự *làm* gì, so với chỉ kiểm rồi bỏ qua. Phần lớn lần chạy của vòng tốt là "đã kiểm, không có gì" |
| **Mục đích** | Một kết quả duy nhất vòng này tồn tại để dịch chuyển |
| **Skill dùng** | Skill marketing nào được điều phối mỗi vòng |
| **Thân vòng** | Các bước theo thứ tự |
| **Tự kiểm tra** | Xác minh *trước khi* hành động — để không hành động vì nhiễu, mùa vụ, ngày sale lớn, hay lỗi đo lường |
| **Trạng thái/chống trùng** | Vòng nhớ gì giữa các lần: dấu lần chạy cuối, khóa chống trùng, thời gian chờ, tập "đã xử lý". Không có thì vòng làm hai lần, nhắc cùng một người, báo cùng một cảnh báo. Bắt buộc với mọi thứ chạy theo lịch — [references/loop-state.md](references/loop-state.md) |
| **Dừng/thoát** | Khi nào bỏ qua, dừng, chuyển cho người, hoặc tự tắt — và làm gì khi lỗi. Vòng nào cũng cần, kể cả vòng "nhịp tim" (dừng = tắt tay + dừng khi lỗi) |
| **Đầu ra** | Kết quả đi đâu: tệp, bản nháp chờ duyệt, thông báo, báo cáo |

Tách **Nhịp kiểm tra / Hành động khi**: vòng theo dõi khách sắp rời có thể *kiểm* hằng ngày nhưng chỉ *làm* khi một tài khoản vượt ngưỡng rủi ro mà chưa được liên hệ trong thời gian chờ. Gộp hai thứ thì hoặc lỡ cửa sổ, hoặc spam.

## Luật nhịp

| Tín hiệu | Nhịp thực tế | Vì sao |
|---|---|---|
| Thứ hạng, backlink, uy tín tên miền | Hằng tuần | Đổi chậm; kiểm hằng ngày là nhiễu |
| Quảng cáo mỏi, CPA trôi | 2–3 ngày | Vòng phản hồi Meta/Google/TikTok tính bằng ngày |
| Phễu kích hoạt | Hằng tuần | Cần đủ lượt đăng ký |
| Tín hiệu rời bỏ | Hằng ngày hoặc khi kích hoạt | Cửa sổ can thiệp ngắn |
| Nội dung xuống cấp | Hằng tháng | Traffic hao mòn từ từ |
| Đối thủ thay đổi | Hằng tuần | Ít đổi nhưng quan trọng |
| Nhắc tới thương hiệu, bình luận | Hằng ngày | Cửa sổ tương tác đóng nhanh |
| Đánh giá xấu trên sàn/Google | Hằng ngày | Phản hồi nhanh giữ điểm shop |
| Giá và khuyến mại đối thủ trên sàn | Hằng tuần; hằng ngày trong mùa sale | Biến động mạnh quanh ngày đôi |

Vòng chạy quá dày là lỗi phổ biến nhất: tạo việc vặt, đốt ngân sách, và dạy mọi người lờ đi kết quả.

## Khi nào KHÔNG nên lặp

- **Chiến lược hoặc định hướng sáng tạo là việc chính** — vòng lặp duy trì và tối ưu, không đặt định vị hay sáng tác chiến dịch.
- **Hành động đăng hoặc chi tiền không qua duyệt.** Tự *soạn nháp* quảng cáo, email, bài đăng, tin Zalo thì được. Tự *đăng* hoặc tự *dời ngân sách* cần điểm duyệt của người, trừ khi người dùng đã cho phép rõ và đặt rào chắn (trần chi, danh sách cho phép).
- **Tín hiệu quá thưa để có ý nghĩa** — vòng tỷ lệ chuyển đổi tuần trên 40 lượt truy cập/tuần là đo nhiễu.
- **Vòng phù phiếm** — không ai hành động theo đầu ra thì xóa.

Mọi vòng gửi tin, chi tiền, đăng bài hoặc chạm dữ liệu cá nhân: áp dụng [loop-guardrails.md](references/loop-guardrails.md) — mô hình hai tầng (tự làm an toàn vs phải duyệt), trần chi/trần gửi, danh sách luôn chuyển người, công tắc dừng bắt buộc. Tài liệu đó dẫn luật Mỹ/EU (CAN-SPAM, GDPR, FTC); với Việt Nam thay bằng: **Nghị định 91/2020** (chỉ gửi khi đã đồng ý, khung giờ tin nhắn 7h–22h, gọi 8h–17h, có cách từ chối), **Luật BVDLCN 2025**, **Luật Quảng cáo** (công khai nội dung trả tiền), điều khoản của Zalo, Meta, TikTok, sàn ([vn-legal.md](references/vn/vn-legal.md)). Vòng gửi tin phải tôn trọng khung giờ và danh sách từ chối.

## Lên lịch

Thân vòng lặp chạy được trên mọi agent; cách lên lịch tùy môi trường:
- **App Claude:** dùng tính năng tác vụ theo lịch (scheduled tasks) nếu tài khoản và môi trường có — mỗi lần chạy là một phiên mới, nên lời nhắc phải tự đầy đủ (đọc trạng thái ở đâu, ghi kết quả ở đâu). Trạng thái lưu trong tệp/Project/công cụ được kết nối, không dựa vào trí nhớ hội thoại.
- **Claude Code:** `/loop` (tự điều nhịp tới khi đạt điều kiện), các công cụ lịch của môi trường, hoặc cron.
- **Agent bất kỳ + cron:** gói thân vòng thành lời nhắc/script theo lịch (`0 9 * * 1` = 9h sáng thứ Hai).
- **Nhịp thủ công:** với vòng cần phán đoán cao, "chạy skill này mỗi sáng thứ Hai" là vòng lặp hoàn toàn hợp lệ — giá trị nằm ở *thân* lặp lại được, không phải tự động hóa.

Mặc định lịch theo giờ cố định cho vòng dạng báo cáo (báo cáo tuần, theo dõi thứ hạng); nhịp động cho vòng theo dõi tới ngưỡng (khách sắp rời, ngày ra mắt, ngày sale). Đặt giờ chạy theo giờ Việt Nam (GMT+7) và tránh khung giờ cấm gửi tin.

## Danh mục và bộ vận hành

- [loop-catalog.md](references/loop-catalog.md) — 60 vòng phủ cả phễu: SEO & nội dung, quảng cáo, kênh tự nhiên/mạng xã hội/đối tác, outbound, kích hoạt, giữ chân, doanh thu, giới thiệu, vận hành.
- **Bộ vận hành SEO** (agent sở hữu SEO cả website): [references/seo-operator.md](references/seo-operator.md) — gộp các vòng SEO vào một lịch, bộ nhớ chung trong `.agents/seo/`, checklist lần đầu, cổng viết, báo cáo tuần một màn hình.
- **Bộ vận hành outbound** (quét tín hiệu, chuẩn bị tiếp cận, phân loại phản hồi, sức khỏe tên miền gửi, rút kinh nghiệm chuỗi hằng tuần): [references/outbound-operator.md](references/outbound-operator.md) — áp dụng thêm pháp lý Việt Nam trong `cold-email`.

**Vòng gợi ý cho SME Việt** (điều chỉnh từ danh mục): báo cáo tuần đa kênh (website + sàn + quảng cáo + chat, tính bằng code từ tệp xuất); theo dõi đánh giá 1–3 sao trên sàn/Google Maps và soạn nháp phản hồi; theo dõi giá/khuyến mại đối thủ trên sàn trước ngày đôi; quảng cáo mỏi (tần suất tăng, CTR giảm) → soạn nội dung thay thế chờ duyệt; nhắc gia hạn gói/mua lại theo chu kỳ (`churn-prevention`).

## Tự viết vòng mới

Không có vòng phù hợp → dùng [references/loop-template.md](references/loop-template.md): mẫu có gợi ý điền, ví dụ trước/sau, checklist trước khi chạy. Điền đủ chín phần; không trả lời cụ thể được tự kiểm tra, trạng thái/chống trùng và dừng/thoát thì vòng chưa sẵn sàng.

## Phản mẫu

- Lặp không có điều kiện dừng → chi tiêu mất kiểm soát
- Cùng một nhịp cho mọi vòng → phần lớn chạy quá dày và bị lờ
- Không tự kiểm tra → hành động vì nhiễu, mùa vụ, ngày sale, lỗi đo lường
- Không có điểm duyệt cho hành động chi tiền/đăng bài
- Dựng 10 vòng cùng lúc → bắt đầu một vòng, chứng minh giá trị, rồi thêm

**Tránh từ ngữ:** "cài một lần rồi quên", "marketing tự động hoàn toàn", "AI làm hết", "tăng 10 lần tự động". Vòng lặp là hệ thống có kỷ luật và điểm duyệt, không phải phép màu.

## Skill liên quan

- `marketing-ideas` — chiến thuật làm một lần; vòng lặp vận hành những cái đáng lặp lại
- `ab-testing` — vòng thử nghiệm
- `analytics` — phần lớn vòng đọc số liệu để quyết định có hành động không
- `reverse-engineer-marketing` — vòng theo dõi nước đi tăng trưởng của đối thủ
- Skill theo kênh (`ads`, `seo-audit`, `emails`, `zalo`, `social`, `marketplaces`, `churn-prevention`, `pricing`, `referrals`) — thân vòng điều phối các skill này
