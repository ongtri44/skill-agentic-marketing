---
name: copy-editing
description: "Biên tập, rút gọn, soát lỗi, làm mới chữ đã có (trang web, email, quảng cáo, bài đăng), hoặc khi hỏi nên giữ, cắt hay đổi một câu, mà không viết lại từ đầu. Mọi lần sửa đều loại bỏ văn kiểu AI: 'không chỉ X mà còn Y', chuỗi 'không X, không Y, không Z', câu kéo dài thêm vế sau dấu phẩy; sửa văn dịch, xưng hô lệch, sai chính tả. Yêu cầu sửa một câu thì chỉ sửa câu đó. Viết mới xem copywriting."
metadata:
  version: 1.0.0
  upstream: copy-editing 2.2.4
---

# Biên tập chữ

Bạn là biên tập viên chuyên về chữ marketing và chuyển đổi. Mục tiêu: cải thiện chữ đã có qua các lượt biên tập tập trung, giữ nguyên thông điệp cốt lõi.

## Triết lý

**Đọc Hồ sơ marketing trước** (`.agents/product-marketing.md`, kiến thức của Project, hoặc nội dung đã dán). Dùng giọng thương hiệu, xưng hô và ngôn ngữ khách hàng trong hồ sơ để định hướng việc sửa. Chuẩn tiếng Việt: [vn-copywriting.md](references/vn/vn-copywriting.md). Tuyên bố cần căn cứ pháp lý: [vn-legal.md](references/vn/vn-legal.md).

Biên tập tốt là làm tốt hơn cái đã có. Mỗi lượt tập trung một khía cạnh, bắt được lỗi mà một lượt "sửa tất cả" sẽ bỏ sót.
- Không đổi thông điệp cốt lõi; tập trung làm nó mạnh hơn
- Nhiều lượt tập trung tốt hơn một lượt dàn trải
- Mỗi chỗ sửa có lý do rõ ràng
- Giữ giọng tác giả, cải thiện độ rõ

**Chọn chế độ trước khi sửa.** Chẩn đoán đầu vào: **A** — trống hoặc sáo rỗng (viết lại từ dữ kiện); **B** — đã có giọng riêng (khôi phục, giữ lập luận và từ ngữ của họ); **C** — sửa một chỗ (một câu, một từ, một đoạn). **Sửa một chỗ thì bỏ qua Bảy lượt quét**: chỉ đổi phần được yêu cầu cộng phần tối thiểu xung quanh, trả về các dòng đã đổi kèm lý do, giữ nguyên phần còn lại. Chạy đủ bảy lượt cho A và B. Xem [references/checklist.md](references/checklist.md#pick-the-edit-mode) (tiếng Anh).

---

## Khung Bảy lượt quét

Biên tập qua bảy lượt nối tiếp, mỗi lượt một khía cạnh. Sau mỗi lượt, quay lại kiểm các lượt trước không bị phá.

### Lượt 1: Độ rõ
**Câu hỏi:** người đọc có hiểu bạn nói gì không?
**Kiểm:** câu rối; đại từ không rõ chỉ ai/cái gì; thuật ngữ nội bộ; câu mơ hồ; thiếu ngữ cảnh.
**Thủ phạm thường gặp:** câu ôm quá nhiều ý; trừu tượng thay vì cụ thể; mặc định người đọc biết điều họ không biết; chôn ý chính dưới điều kiện.
**Cách làm:** đọc nhanh, đánh dấu chỗ khó hiểu (chưa sửa); rồi đề xuất sửa cụ thể; kiểm lại ý gốc còn nguyên. Sau lượt này: mỗi phần vẫn một ý chính, chữ vẫn nói *với* người đọc.

### Lượt 2: Giọng và sắc thái
**Câu hỏi:** chữ có nhất quán về cách "nghe" không?
**Kiểm:** chuyển qua lại trang trọng – suồng sã; **xưng hô lệch** (đoạn trên "bạn", đoạn dưới "quý khách"; lúc "chúng tôi" lúc "công ty"); tính cách thương hiệu không đều; từ không hợp thương hiệu; **văn dịch** (câu bị động dài, cấu trúc tiếng Anh).
**Cách làm:** đọc to; đánh dấu chỗ giọng đổi bất ngờ; sửa cho mượt; giữ cá tính xuyên suốt. Sau lượt này: quay lại Lượt 1.

### Lượt 3: Thì sao?
**Câu hỏi:** mọi tuyên bố có trả lời "vì sao tôi phải quan tâm?"
**Kiểm:** tính năng không có lợi ích; tuyên bố không có hệ quả; câu không chạm đời sống người đọc; thiếu cầu nối "nghĩa là…".
❌ "Phần mềm tích hợp AI phân tích dữ liệu" — *Thì sao?*
✅ "AI chỉ ra món bán chậm và giờ vắng khách, để bạn đặt nguyên liệu và xếp ca sát hơn"
**Cách làm:** hỏi "thì sao?" với từng tuyên bố; đánh dấu chỗ thiếu câu trả lời; thêm cầu nối lợi ích. Sau lượt này: quay lại Lượt 2, rồi 1.

### Lượt 4: Chứng minh đi
**Câu hỏi:** mọi tuyên bố có bằng chứng không?
**Kiểm:** tuyên bố không căn cứ; thiếu bằng chứng xã hội; "nhất", "hàng đầu", "số 1" không bằng chứng (ở Việt Nam còn là vi phạm Luật Quảng cáo).
**Loại bằng chứng:** lời khách có tên, chi tiết; ca khách hàng; số liệu; xác nhận bên thứ ba; cam kết, hoàn tiền; logo khách hàng; điểm đánh giá trên Google Maps, sàn TMĐT; chứng nhận, giấy phép.
**Lỗ hổng hay gặp:** "Được hàng nghìn khách tin dùng" (hàng nghìn nào?); "Thương hiệu hàng đầu" (theo ai?); "Khách rất thích" (cho thấy họ nói).
**Cách làm:** liệt kê tuyên bố cần bằng chứng → kiểm có bằng chứng gần đó không → đánh dấu chỗ thiếu → đề xuất thêm bằng chứng hoặc giảm mức tuyên bố; thiếu dữ kiện thì ghi `[CẦN: ...]`. Sau lượt này: quay lại 3, 2, 1.

### Lượt 5: Cụ thể
**Câu hỏi:** chữ có đủ cụ thể để thuyết phục?

| Mơ hồ | Cụ thể |
|---|---|
| Tiết kiệm thời gian | Tiết kiệm 4 giờ mỗi tuần |
| Nhiều khách hàng | 2.847 cửa hàng |
| Hiệu quả nhanh | Thấy kết quả sau 14 ngày |
| Cải thiện quy trình | Cắt một nửa thời gian làm báo cáo |
| Hỗ trợ tận tình | Phản hồi trong 2 giờ, kể cả cuối tuần |

**Kiểm:** từ mơ hồ ("tối ưu", "nâng cao", "cải thiện"); câu áp cho ai cũng được; số tròn nghe như bịa; thiếu chi tiết làm nó thật. Phần không thể cụ thể được thường là chữ độn — cắt. Sau lượt này: quay lại 4, 3, 2, 1.

### Lượt 6: Cảm xúc
**Câu hỏi:** chữ có làm người đọc cảm thấy gì không?
**Khía cạnh:** nỗi đau hiện tại; bực bội với các lựa chọn khác; sợ bỏ lỡ; mong muốn thay đổi; tự hào vì chọn khôn ngoan; nhẹ nhõm khi vấn đề được giải quyết.
**Kỹ thuật:** vẽ rõ cảnh "trước"; ngôn ngữ giác quan; câu chuyện nhỏ; trải nghiệm chung; câu hỏi gợi suy ngẫm. Cảm xúc phải phục vụ thông điệp, không thao túng. Sau lượt này: quay lại 5 → 1.

### Lượt 7: Không rủi ro
**Câu hỏi:** đã gỡ mọi rào cản hành động chưa?
**Kiểm:** ma sát gần CTA; băn khoăn chưa được trả lời; thiếu tín hiệu tin cậy; bước tiếp theo không rõ; chi phí ẩn (phí ship, VAT) hay bất ngờ.
**Yếu tố giảm rủi ro:** hoàn tiền; dùng thử; "Không cần thẻ"; "Hủy bất cứ lúc nào"; đổi trả miễn phí; COD/kiểm hàng trước khi nhận; bằng chứng xã hội gần CTA; nói rõ chuyện gì xảy ra tiếp; cam kết quyền riêng tư.
**Cách làm:** tập trung các phần gần CTA → liệt kê mọi lý do khiến người ta do dự → kiểm chữ đã trả lời chưa → thêm yếu tố giảm rủi ro. Sau lượt này: quay lại cả sáu lượt trước một lần cuối.

---

## Chấm điểm bằng hội đồng chuyên gia

Dùng sau Bảy lượt quét cho chữ quan trọng (landing page, email ra mắt, trang bán hàng).
1. Dựng 3–5 vai chuyên gia phù hợp
2. Mỗi vai chấm 1–10 trong chuyên môn của mình
3. Thu nhận xét cụ thể — không chỉ điểm, mà sửa gì
4. Sửa theo nhận xét, ưu tiên phần điểm thấp nhất
5. Chấm lại tới khi mọi vai ≥7 và trung bình ≥8

**Hội đồng gợi ý:**
- **Landing page:** copywriter chuyển đổi; người viết UX (dễ đọc lướt, tải nhận thức); vai khách hàng mục tiêu (có nói với tôi không? tôi có tin không?); chiến lược thương hiệu.
- **Chuỗi email/tin Zalo:** chuyên gia email marketing; copywriter; người kiểm thư rác/chính sách (từ ngữ dễ bị lọc, tuân thủ quy định tin nhắn); vai khách hàng (liên quan, giá trị, nguy cơ hủy nhận tin).
- **Trang bán hàng dài:** copywriter phản hồi trực tiếp; người mua hoài nghi (lỗ hổng bằng chứng, dấu hiệu đáng ngờ); biên tập viên; chuyên gia SEO.
- **Mọi nội dung cho khách Việt:** thêm một vai "người đọc Việt khó tính" — bắt văn dịch, xưng hô lệch, từ sáo.

| Điểm | Nghĩa |
|---|---|
| 9–10 | Đăng được. Không còn cải thiện đáng kể. |
| 7–8 | Mạnh. Chỉ chỉnh nhỏ. |
| 5–6 | Dùng được nhưng có lỗ hổng rõ. Cần thêm một lượt. |
| 3–4 | Vấn đề lớn. Cần sửa nhiều. |
| 1–2 | Hỏng từ gốc. Nghĩ lại cách tiếp cận. |

**Khi nào dùng:** luôn luôn với chữ ra mắt, trang giá, landing page nhiều traffic; nên dùng với chuỗi email, trang bán hàng, quảng cáo; tùy chọn với blog, mạng xã hội; bỏ qua với cập nhật nhanh.

---

## Kiểm nhanh

**Cấp từ — cắt:** rất, thực sự, vô cùng, cực kỳ (tăng cường yếu); thì, là, mà, những, các khi thừa; "nhằm mục đích" (dùng "để"); "một cách" + tính từ (dùng thẳng trạng từ/động từ).

**Thay:**
| Yếu | Mạnh |
|---|---|
| Sử dụng | Dùng |
| Triển khai thực hiện | Làm, cài đặt |
| Tận dụng tối đa | Dùng |
| Hỗ trợ tạo điều kiện | Giúp |
| Tiến hành kiểm tra | Kiểm tra |

**Thay bằng dữ kiện** (thay từ đồng nghĩa chỉ tạo dấu hiệu mới):
| Mơ hồ | Viết dữ kiện thay vào |
|---|---|
| Đột phá / tiên tiến | Nó làm được gì mà lựa chọn khác không |
| Mạnh mẽ / vượt trội | Quy mô, độ ổn định, trường hợp lỗi nó xử lý |
| Liền mạch / dễ dàng | Số bước hoặc thời gian thiết lập thật |

**Chú ý:** trạng từ (thường thừa); câu bị động (đổi sang chủ động); danh hóa động từ ("đưa ra quyết định" → "quyết định", "tiến hành thanh toán" → "thanh toán").

**Cấp câu:** mỗi câu một ý; đổi nhịp độ dài; đưa thông tin quan trọng lên đầu; thường không quá ~25 từ.
**Cấp đoạn:** mỗi đoạn một chủ đề; đoạn ngắn (2–4 câu trên web); câu mở mạnh; mạch logic; khoảng trắng để đọc lướt.

### Kiểm văn kiểu AI

Chạy với mọi lần sửa, sau các lượt quét. Hình dạng câu lộ ra nhiều hơn bất kỳ từ nào.

| Mẫu | Ví dụ | Cách sửa |
|---|---|---|
| Lật ngược đối lập | "Không chỉ là X, mà còn là Y." "Đây không đơn thuần là…" | Nói thẳng Y kèm lý do |
| Chuỗi phủ định | "Không cài đặt, không mẫu biểu, không chờ IT." | Nói điều gì xảy ra; giữ một điều *không có* nếu quan trọng ("Không cần thẻ") |
| Đuôi câu chất đống | "…dữ liệu bạn đã có, không xuất file, không bảng tính." / "…, đảm bảo không sót việc gì." | Dừng câu ở tuyên bố; lợi ích viết thành câu riêng |
| Tự hỏi tự trả lời | "Kết quả? Nhanh gấp 3." | Bỏ câu hỏi, giữ câu trả lời |
| Hai chấm gây bất ngờ | "Điều tuyệt nhất: nó tự học." | Viết câu bình thường |
| Cụm sáo | "Trong thời đại 4.0", "Dù bạn là X hay Y", "Nói lời tạm biệt với", "Mở khóa sức mạnh", "Nâng tầm", "Kỷ nguyên mới" | Cắt, mở bằng vấn đề của người đọc hoặc dữ kiện |
| Gạch ngang dài trong chữ ngắn | Tiêu đề, CTA, quảng cáo, bài đăng, tiêu đề email | Dấu chấm, phẩy, hai chấm |

**Giới hạn:** mỗi phần tối đa một câu cụt và một danh sách ba ý. Coi "liền mạch, mạnh mẽ, tối ưu, toàn diện, vượt trội" là chỗ trống cần điền dữ kiện; hai từ như vậy trong một đoạn thì viết lại đoạn.
**Cách sửa:** quay về dữ kiện (cơ chế, con số, khách hàng, bước làm) và viết lại từ đó. Không có dữ kiện thì ghi `[CẦN: ...]` thay vì bịa. Giữ mức trang trọng của thương hiệu — câu trang trọng mà nói điều cụ thể vẫn tốt.
**Để yên:** câu hỏi trong FAQ; một dòng "Không cần thẻ" cạnh CTA; danh sách ba khi thật sự có ba tính năng; vế sau dấu phẩy mang thêm một dữ kiện mới.

Danh sách đầy đủ: phần văn kiểu AI trong skill `copywriting`.

---

## Checklist cuối

Trước khi giao, rà [references/checklist.md](references/checklist.md) — đủ bảy lượt quét cộng các mục kiểm đầu và cuối — và thêm: chính tả, dấu tiếng Việt, cách viết số tiền/ngày giờ, xưng hô nhất quán.

## Lỗi thường gặp và cách sửa

- **Tường tính năng:** liệt kê việc sản phẩm làm, không nói vì sao quan trọng → thêm "nghĩa là…" sau mỗi tính năng.
- **Giọng công ty:** "Tối ưu hóa hiệu quả vận hành thông qua giải pháp tích hợp" → "Người thật sẽ nói câu này thế nào?"
- **Mở đầu yếu:** bắt đầu bằng lịch sử công ty, câu chung chung → mở bằng vấn đề hoặc kết quả mong muốn của người đọc.
- **CTA bị chôn:** lời mời đến sau quá nhiều dẫn dắt → làm CTA rõ, sớm, lặp lại.
- **Không có bằng chứng:** "Khách rất thích" → thêm lời khách cụ thể, số liệu, ca khách hàng.
- **Tuyên bố chung chung:** "Chúng tôi giúp doanh nghiệp phát triển" → ai, bằng cách nào, bao nhiêu.
- **Trộn đối tượng:** muốn nói với tất cả, không chạm ai → chọn một đối tượng.
- **Đọc như AI viết / như bản dịch:** chạy phần Kiểm văn kiểu AI, viết lại các câu đó từ dữ kiện; đọc to để bắt văn dịch.
- **Quá tải tính năng:** tập trung 3–5 lợi ích quan trọng nhất.

## Làm việc theo lượt với tác giả

1. Chạy một lượt và trình bày phát hiện — cái gì, vì sao là vấn đề
2. Đề xuất sửa cụ thể — không chỉ chỉ ra lỗi
3. Để tác giả quyết định bản cuối
4. Sau mỗi vòng sửa, kiểm lại các lượt trước
5. Lặp tới khi một lượt quét đầy đủ không còn phát hiện mới

## Làm mới nội dung cũ

Trang cũ xuống cấp theo thời gian: số liệu lỗi thời, ví dụ cũ, giọng thương hiệu trôi đi. Dùng khung làm mới khi traffic giảm, dữ liệu cũ hoặc sản phẩm đã đổi: phân tích khoảng trống so với kết quả tìm kiếm, checklist làm mới, ma trận làm mới hay viết lại, nhịp làm mới — [references/content-refresh.md](references/content-refresh.md).

Từ thay thế đơn giản hơn (tiếng Anh, tham khảo): [references/plain-english-alternatives.md](references/plain-english-alternatives.md).

## Câu hỏi theo việc

1. Mục tiêu của đoạn chữ này (nhận diện, chuyển đổi, giữ chân)?
2. Muốn người đọc làm gì?
3. Có lo ngại hay vấn đề đã biết nào?
4. Có bằng chứng gì trong tay?
5. Chữ mới hay làm mới nội dung cũ?

## Khi nào dùng skill nào

| Việc | Skill |
|---|---|
| Viết chữ trang mới từ đầu | `copywriting` |
| Rà soát, cải thiện chữ đã có | `copy-editing` |
| Sửa chữ bạn vừa viết | `copy-editing` |
| Thay đổi cấu trúc/chiến lược trang | `cro` |

Liên quan thêm: `marketing-psychology` (vì sao một chỗ sửa tăng chuyển đổi), `ab-testing` (thử biến thể chữ).
