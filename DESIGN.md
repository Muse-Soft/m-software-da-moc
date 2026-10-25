# DESIGN.md — Landing page xưởng đồ da thủ công Da Mộc

> Tài liệu thiết kế chốt cho sprint TEC-397 (task Thiết kế TEC-398). Dev (task Dev của sprint) dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách. QA đối chiếu bản dựng với tài liệu này, kèm kiểm tra đa dạng theo OPERATIONS.md mục 16.5.

## 0. Khác biệt so với các project gần nhất (bắt buộc theo mục 16.5 — đã đọc thật ngày 2026-10-26)

Thứ tự project mới nhất lấy từ https://msoft.genalpha.dev/api/office, DESIGN.md đọc trực tiếp qua raw.githubusercontent.com ngày 2026-10-26 (repo tarotlight-app là private nên không đọc trực tiếp được; nội dung của nó lấy theo DESIGN.md đã ghi trong hồ sơ Kim Ngọc TEC-371 và Đắng Ngọt TEC-384, trong đó app này tự ghi là không có archetype bố cục web):

| Project (mới → cũ) | Archetype | Cặp font | Nhiệt màu |
|---|---|---|---|
| Đắng Ngọt (m-software-dang-ngot, TEC-384) | A5 Theo chương | Fraunces + Be Vietnam Pro | Sáng-ấm (nền `#F3E9D7`) |
| Kim Ngọc (m-software-kim-ngoc, TEC-371) | A2 Split | Noto Serif Display + Manrope | Tối-ấm (nền `#141210`) |
| TarotLight (tarotlight-app, TEC-352) | Không có archetype web (app mobile Flutter, tự ghi "BỎ QUA luật đa dạng archetype") | Cormorant Garamond + (nội dung) | Tối (nền tím đêm `#120E24`) |

Lựa chọn cho Da Mộc và lý do không vi phạm luật chống trùng (§16.5):

- **Archetype: A1 Editorial dọc** — KHÁC A5 của Đắng Ngọt (project web liền trước) và KHÁC A2 của Kim Ngọc (project web liền trước nữa); TarotLight không có archetype web nên không tính trùng. Cách A1 thể hiện ở: trang đọc như một bài tạp chí dọc — ảnh lớn toàn chiều rộng khối xen kẽ đoạn văn ngắn, khoảng trắng lớn giữa các khối, không chia đôi màn hình cố định (A2), không chia chương đánh số (A5), không dùng lưới bento hay thanh bên cố định.
- **Cặp font: Playfair Display + Be Vietnam Pro** — KHÁC nguyên cặp Fraunces + Be Vietnam Pro của project liền trước (Đắng Ngọt): font tiêu đề đổi từ Fraunces sang Playfair Display, chỉ font nội dung giữ Be Vietnam Pro. Vì vậy KHÔNG lặp nguyên cặp, không vi phạm; giữ đúng tinh thần công thức gợi ý trong yêu cầu (serif cổ điển cho xưởng thủ công châu Âu).
- **Nhiệt màu: TỐI-ẤM — KHÔNG CẦN ĐỔI:** công thức gợi ý trong yêu cầu đặt nền chính tối `#1F1A15`. Chuỗi nhiệt sau khi giữ nguyên: Da Mộc (tối-ấm) → Đắng Ngọt (sáng-ấm) → Kim Ngọc (tối-ấm): không có 3 project liên tiếp cùng nhiệt màu vì Đắng Ngọt sáng-ấm đứng giữa, nên giữ nguyên nền tối gợi ý mà không vi phạm "tránh 3 project liên tiếp cùng một nhiệt màu chủ đạo".
- **Điểm nhấn riêng** (xem mục "Điểm nhấn đặc sắc"): đường chỉ khâu yên ngựa + tem da dập nổi — không project nào gần đây có.

## Tổng quan

- Sản phẩm: landing page 1 trang, visual-first, cho xưởng đồ da thủ công Da Mộc — làm tay ví, túi, thắt lưng, đồ da đặt riêng theo yêu cầu.
- Archetype: **A1 Editorial dọc** — bài tạp chí dọc: ảnh lớn toàn chiều rộng, đoạn văn ngắn, khoảng trắng rộng.
- Phong cách tham chiếu: **xưởng thủ công châu Âu cổ điển** — bàn gỗ sẫm, dụng cụ da cũ, ánh đèn vàng ấm, cận cảnh vân da và đường chỉ khâu tay; không dùng ảnh studio trắng, không dùng tông lạnh.
- Ngôn ngữ: tiếng Việt, hỗ trợ dấu đầy đủ (cả Playfair Display và Be Vietnam Pro đều hỗ trợ tiếng Việt).

## Bảng màu (mã hex + vai trò)

| Mã hex | Vai trò |
|---|---|
| `#1F1A15` | Nền chính toàn trang — nâu đen da thuộc sẫm, tối-ấm |
| `#2A231C` | Nền khối phụ xen kẽ (khối bộ sưu tập, khối cảm nhận) và nền thẻ |
| `#F1E7D3` | Chữ chính + tiêu đề — kem da thuộc sáng, tương phản cao trên nền tối |
| `#B8A88F` | Chữ phụ (mô tả ngắn, chú thích ảnh, ghi chú giá mẫu) — be xám ấm |
| `#C68B4A` | Nhấn chính — vàng đồng da bò: nút bấm, giá mẫu, đường chỉ khâu, tem da |
| `#8A5A2B` | Nhấn phụ — nâu da đậm: viền ảnh, đường kẻ mảnh, chi tiết trang trí nhỏ; không làm nền khối lớn |

Quy tắc dùng màu: nền luôn là tối (`#1F1A15` hoặc `#2A231C` xen kẽ theo khối); không dùng khối nền sáng toàn trang; màu nhấn `#C68B4A` chỉ dùng cho nút, giá, điểm nhấn — không tô nền lớn bằng màu nhấn.

## Typography

- Font tiêu đề: **Playfair Display** (serif cổ điển, nét tương phản cao) — tên xưởng ở hero 64px desktop / 40px mobile; tiêu đề khối 40px desktop / 28px mobile; tên sản phẩm da 24px.
- Font nội dung: **Be Vietnam Pro** — thân bài 17px, dòng cách 1,6; chú thích ảnh và nhãn tem da 13px, chữ hoa toàn bộ (uppercase), giãn cách chữ 0,08em.
- Không dùng thêm font thứ ba.

## Điểm nhấn đặc sắc

1. **Đường chỉ khâu yên ngựa (saddle stitch)** — đường chia giữa các khối không phải đường thẳng trơn mà là đường nét đứt màu `#C68B4A`, mỗi nét dài 8px, khoảng trống 4px, dày 2px (mô phỏng mũi chỉ khâu tay trên mép da), chạy toàn bộ chiều rộng nội dung; mỗi tiêu đề khối cũng có một đoạn chỉ khâu ngắn 48px ngay trên tiêu đề.
2. **Tem da dập nổi** — mỗi thẻ sản phẩm có một tem nhỏ hình chữ nhật bo góc 4px, nền `#8A5A2B`, viền nét đứt `#C68B4A` (chỉ khâu viền tem), chữ `#F1E7D3` 13px uppercase (ví dụ "LÀM TAY · DA BÒ THUỘC THẢO MỘC"); tem đặt ở góc trên bên trái ảnh sản phẩm, không dùng ở nơi khác.

## Bố cục (A1 Editorial dọc)

Thứ tự khối, không đổi thứ tự, không thêm khối ngoài danh sách:

1. **Hero** — ảnh toàn màn hình thợ đang khâu tay một chiếc ví da; tên xưởng "Da Mộc" + câu định vị một dòng + 1 nút chính "Xem bộ sưu tập" (cuộn xuống khối 2).
2. **Câu chuyện xưởng** — đoạn văn ngắn về người thợ và triết lý làm da tay, kèm 1 ảnh lớn bàn làm da với dụng cụ; chữ chiếm tối đa 60% chiều rộng khối, không dàn 2 cột.
3. **Bộ sưu tập** — mỗi nhóm sản phẩm (ví, túi, thắt lưng, đồ đặt riêng) một khối editorial: ảnh lớn toàn chiều rộng + tên nhóm + mô tả 1–2 câu + giá mẫu; các nhóm xếp dọc từng khối, không xếp lưới nhiều cột, không chia đôi trái/phải cố định.
4. **Quy trình** — đúng 4 bước (Chọn da → Cắt → Khâu tay → Hoàn thiện), mỗi bước một dòng editorial: ảnh bước + số bước + tên bước + mô tả 1–2 câu, xếp dọc; không xếp ngang 4 ô kiểu bảng.
5. **Cảm nhận khách** — 3 cảm nhận ngắn (tên khách để placeholder, không bịa tên thật), mỗi cảm nhận một dòng kèm đường chỉ khâu chia cách.
6. **Đặt hàng / Liên hệ** — form chỉ giao diện (không gửi thật): họ tên, số điện thoại, chọn loại yêu cầu (mua sẵn / đặt riêng), ghi chú; nút "Gửi yêu cầu" chỉ hiển thị, không có xử lý gửi.
7. **Chân trang** — tên xưởng, câu slogan một dòng, ghi chú "Trang demo — giá và form chỉ là mẫu".

Khoảng trắng: giữa hai khối cách nhau tối thiểu 96px desktop / 64px mobile; nội dung chính rộng tối đa 1080px, căn giữa.

## Quy tắc hình ảnh

- Tông ảnh: ấm, ánh sáng vàng, nền gỗ sẫm hoặc da sẫm trong ảnh; tuyệt đối không dùng ảnh ánh sáng trắng lạnh, không dùng ảnh nền trắng studio.
- Tỉ lệ khung: hero toàn màn hình 16:9 trên desktop, cắt giữa thành 4:5 trên mobile (giữ tay thợ ở giữa khung); ảnh câu chuyện 3:2 ngang; ảnh từng nhóm sản phẩm 16:9 ngang, ảnh lớn chiếm gần hết chiều rộng khối; ảnh quy trình 3:2 ngang cho cả 4 bước.
- Nội dung ảnh: hero bắt buộc là thợ đang khâu tay đồ da (kim, chỉ và đường khâu nhìn thấy rõ); ảnh bộ sưu tập là cận cảnh từng sản phẩm da, thấy rõ vân da và đường chỉ; ảnh quy trình theo đúng bước (tấm da → cắt → khâu → thành phẩm).
- Ảnh mẫu: dùng ảnh mẫu chất lượng cao, đồng tông theo quy tắc trên ngay từ bản đầu tiên; ghi rõ là ảnh mẫu trong kết quả của Dev.
- Không dùng ảnh người thật nổi tiếng, không dùng logo thương hiệu thật.

## Quy tắc dữ liệu thật / mẫu (bắt buộc cho Dev)

- Giá trên trang **luôn là giá mẫu**: mỗi giá phải kèm chữ "Giá mẫu" ngay cạnh, footer ghi rõ "Tất cả giá trên trang là giá mẫu".
- Địa chỉ, điện thoại, giờ mở cửa, người phụ trách và tên người cảm nhận để placeholder **`[CẦN BỔ SUNG]`**, tuyệt đối không bịa số liệu thật.
- Form liên hệ/đặt hàng **CHỈ giao diện**: submit dùng preventDefault và hiện thông báo mẫu ("Đây là bản giao diện mẫu — yêu cầu chưa được gửi đi thật"); không có thuộc tính action, không fetch, không mailto:, không tel:.
- Toàn bộ ảnh là ảnh mẫu, footer ghi rõ điều này.

## Quy tắc responsive

- Desktop (≥1024px): nội dung chính rộng tối đa 1080px, căn giữa; ảnh toàn chiều rộng khối.
- Mobile (<768px): một cột duy nhất; hero cắt 4:5; bảng giá giữ dạng dòng (tên + giá), không ép thành bảng nhiều cột ngang gây cuộn ngang.
- Không có cuộn ngang ở bất kỳ breakpoint nào.
