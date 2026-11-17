# Hướng dẫn cài đặt và sử dụng Skill Agentic Marketing

Tải gói tại https://github.com/ongtri44/skill-agentic-marketing. Gói gồm hai phần: thư mục `claude-app/` (mỗi skill một tệp ZIP, dùng cho app Claude trên web và desktop) và `claude-code/` (một plugin cho Claude Code; trên GitHub là thư mục `plugin/`). Chọn phần hợp với bạn.

*Giao diện và tên menu của app Claude có thể thay đổi theo thời gian; nếu không thấy đúng tên dưới đây, xem trang trợ giúp chính thức: https://support.claude.com (bài "Use skills in Claude").*

---

## Phần A — App Claude (web, desktop)

### Điều kiện
- Tài khoản Claude gói Free, Pro, Max, Team hoặc Enterprise.
- Bật **Code execution and file creation** (thực thi mã và tạo tệp) trong phần cài đặt — skill cần tính năng này.
- Gói **Enterprise**: chủ sở hữu tổ chức phải bật Skills trong Organization settings → Skills trước. Gói **Team**: thường đã bật sẵn ở cấp tổ chức.

### Tải skill lên (mỗi người tự làm)
1. Mở Claude trên web hoặc ứng dụng desktop, vào **Customize → Skills**.
2. Bấm **"+"** → **Create skill** → **Upload a skill**.
3. Chọn **một** tệp ZIP trong thư mục `claude-app/` (ví dụ `product-marketing.zip`).
4. Lặp lại cho từng skill muốn dùng. Skill xuất hiện trong danh sách và bật/tắt được bằng công tắc.

Lưu ý:
- **Không** tải tệp ZIP tổng `skill-agentic-marketing-1.0.1.zip` lên — giải nén trước, rồi tải từng tệp trong `claude-app/`.
- Mỗi ZIP đã đúng cấu trúc (thư mục skill nằm trong ZIP, có `SKILL.md`); không giải nén rồi nén lại.
- Skill tải lên là **riêng tư** cho tài khoản của bạn cho tới khi bạn chia sẻ.

### Cho cả công ty (gói Team/Enterprise)
- **Chủ sở hữu tổ chức** có thể cấp skill cho toàn bộ thành viên: Organization settings → Skills → Add → Upload a skill → chọn ZIP. Skill được cấp sẽ tự xuất hiện và bật sẵn cho mọi người (mỗi người vẫn tắt được).
- Hoặc từng người tải lên rồi **Share** cho đồng nghiệp/nhóm (cần quyền chia sẻ do chủ sở hữu bật).

### Bộ khởi đầu gợi ý theo ngành
Luôn có **`product-marketing`**, rồi thêm:

| Loại doanh nghiệp | Skill nên bật |
|---|---|
| Shop online (sàn, TikTok, Facebook) | marketplaces, livestream, chat-selling, ads, ad-creative, social, offers, zalo, copywriting, image |
| Cửa hàng, F&B, quán | local-marketing, social, zalo, offers, referrals, churn-prevention, image, video, directory-submissions |
| Dịch vụ (spa, gym, phòng khám, giáo dục) | local-marketing, chat-selling, zalo, sms, churn-prevention, lead-magnets, ads, social, offers |
| B2B, dịch vụ chuyên nghiệp | sales-enablement, prospecting, cold-email, content-strategy, seo-audit, revops, events, competitor-profiling, marketing-plan |
| Phần mềm, ứng dụng | cro, signup, onboarding, pricing, paywalls, churn-prevention, seo-audit, ai-seo, launch, emails |
| Agency marketing | marketing-plan, customer-research, competitor-profiling, copywriting, copy-editing, ads, ad-creative, analytics, social, content-strategy |

Bật thêm khi cần; tắt bớt skill ít dùng để Claude tập trung hơn.

### Thiết lập Project (khuyến nghị)
1. Tạo một **Project**, ví dụ "Marketing – Tên công ty".
2. Trong Project, gõ: *"Giúp tôi lập Hồ sơ marketing cho doanh nghiệp."* — skill `product-marketing` sẽ hỏi lần lượt (sản phẩm, khách hàng, đối thủ, giọng thương hiệu, xưng hô, kênh bán…).
3. Khi xong, lưu hồ sơ vào **kiến thức của Project** (tải tệp hồ sơ lên hoặc dán nội dung). Mọi cuộc trò chuyện sau trong Project sẽ dùng lại hồ sơ này.
4. Có thể thêm vào kiến thức Project: bảng giá, catalogue, quy định đổi trả, giấy phép/công bố sản phẩm, hướng dẫn thương hiệu — Claude sẽ viết nội dung đúng hơn và đúng luật hơn.

### Dùng hằng ngày
- Hỏi bằng tiếng Việt bình thường; Claude tự chọn skill. Muốn chắc chắn thì gọi tên: *"Dùng skill `livestream` viết kịch bản…"*.
- Đưa số liệu thật: xuất CSV từ Ads Manager, sàn, GA4, phần mềm bán hàng và tải lên; hoặc bật kết nối nếu có.
- Với nội dung quảng cáo, khuyến mại, tin nhắn: đọc phần cảnh báo pháp lý Claude đưa ra trước khi đăng.

---

## Phần B — Claude Code

### Cài dạng plugin (từ GitHub)
Mở Claude Code và chạy:
```
/plugin marketplace add ongtri44/skill-agentic-marketing
/plugin install skill-agentic-marketing@skill-agentic-marketing
```
Chọn phạm vi cài (cho riêng bạn, cho dự án, hoặc cục bộ) khi được hỏi. Kiểm tra: chạy `/plugin` hoặc hỏi *"Có những skill marketing nào?"*.

### Cài dạng plugin (từ tệp ZIP, không cần mạng tới GitHub)
1. Giải nén `skill-agentic-marketing-claude-code.zip` vào một thư mục, ví dụ `~/plugins/` (sẽ có `~/plugins/skill-agentic-marketing/`).
2. Trong Claude Code:
   ```
   /plugin marketplace add ~/plugins/skill-agentic-marketing
   /plugin install skill-agentic-marketing@skill-agentic-marketing
   ```

### Cách khác: chép thư mục skill
Chép các thư mục trong `skills/` (trong repo: `plugin/skills/`) vào `~/.claude/skills/` (dùng cho mọi dự án) hoặc `.claude/skills/` trong dự án.

### Hồ sơ marketing trong dự án
Skill `product-marketing` lưu hồ sơ ở `.agents/product-marketing.md` (cũng đọc được `.claude/product-marketing.md`). Commit tệp này vào kho mã để cả đội dùng chung.

### Thư mục `tools/`
Chứa hướng dẫn tích hợp công cụ và CLI của bộ gốc (tiếng Anh). Skill dẫn tới khi cần; script chỉ chạy khi bạn yêu cầu.

### Skill từ app Claude sang Claude Code
Skill bạn đã tải lên app Claude có thể đồng bộ sang Claude Code khi đăng nhập cùng tài khoản (Claude Code bản mới; chạy `/skills` để xem). Nếu đã cài plugin, tránh bật trùng cùng một skill ở cả hai nơi.

---

## Cập nhật lên bản mới
- **App Claude:** xóa skill cũ trong Customize → Skills rồi tải ZIP mới lên (giữ nguyên hồ sơ trong Project).
- **Claude Code:** cài từ GitHub thì chạy `/plugin marketplace update skill-agentic-marketing` (hoặc gỡ và cài lại).

## Xử lý sự cố

| Vấn đề | Cách xử lý |
|---|---|
| Không tải lên được | Kiểm tra đã bật thực thi mã; tải đúng ZIP của từng skill, không phải ZIP tổng; không nén lại thư mục |
| Skill không tự kích hoạt | Kiểm tra skill đang bật; hỏi cụ thể hơn; hoặc gọi tên skill trong câu hỏi |
| Claude hỏi lại thông tin cơ bản mỗi lần | Lưu Hồ sơ marketing vào kiến thức Project (app) hoặc `.agents/product-marketing.md` (Claude Code) |
| Câu trả lời lẫn tiếng Anh | Nói "trả lời bằng tiếng Việt"; tài liệu tham khảo sâu là tiếng Anh nên đôi khi giữ thuật ngữ gốc |
| Thông tin pháp lý/số liệu có vẻ cũ | Yêu cầu Claude tìm kiếm kiểm tra lại (nếu bật tìm kiếm web); cập nhật gói lên bản mới |

## Kiểm tra skill kích hoạt đúng (tùy chọn)
Tệp `evals/prompts-vi.json` có 116 câu lệnh tiếng Việt (2 câu mỗi skill) kèm skill mong đợi. Bật toàn bộ skill, gửi từng câu trong cuộc trò chuyện mới và ghi lại skill được dùng — hữu ích khi bạn chỉnh mô tả skill hoặc phát hành bản mới.
