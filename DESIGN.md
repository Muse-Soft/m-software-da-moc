# DESIGN.md — Landing page xưởng đồ da thủ công Da Mộc

> Tài liệu thiết kế chốt cho sprint TEC-397 (task Thiết kế TEC-398). Dev (task Dev của sprint) dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách. QA đối chiếu bản dựng với tài liệu này, kèm kiểm tra đa dạng theo OPERATIONS.md mục 16.5.

## 0. Khác biệt so với các project gần nhất (bắt buộc theo mục 16.5 — đã đọc thật ngày 2026-10-25)

Thứ tự project mới nhất lấy từ https://msoft.genalpha.dev/api/office; DESIGN.md đọc trực tiếp qua raw.githubusercontent.com ngày 2026-10-25 (repo tarotlight-app là private nên không tính archetype web):

| Project (mới → cũ) | Archetype | Cặp font | Nhiệt màu |
| Đắng Ngọt (m-software-dang-ngot, TEC-384) | A5 Theo chương | Fraunces + Be Vietnam Pro | Sáng-ấm (nền `#F3E9D7`) |
| Kim Ngọc (m-software-kim-ngoc, TEC-371) | A2 Split | Noto Serif Display + Manrope | Tối-ấm (nền `#141210`) |
| Bánh Lăn (m-software-banh-lan, TEC-347) | A6 Thanh bên cố định | Fraunces + Be Vietnam Pro | Sáng-ấm (nền `#ECEAE4`) |

- **Archetype: A3 Lệch tâm** — KHÁC A5 của Đắng Ngọt (project liền trước) và KHÁC A2 của Kim Ngọc (project liền trước nữa); cũng khác A6 của Bánh Lăn. Cách A3 thể hiện ở: hero và các khối đều lệch trục — ảnh lớn chiếm 55–65% chiều ngang lệch trái hoặc phải luân phiên, khối chữ chồng lấn lên mép ảnh 8–12% (xem mục "Bố cục"), không phải chia chương đánh số (A5), không phải chia đôi đều hai bên (A2), không phải thanh bên cố định (A6).
- **Cặp font: Playfair Display + Be Vietnam Pro** — KHÁC nguyên cặp Fraunces + Be Vietnam Pro của project liền trước (Đắng Ngọt): font tiêu đề đổi sang Playfair Display (serif cổ điển, chân chữ thanh mảnh, hợp xưởng da châu Âu cổ điển, hỗ trợ tiếng Việt). Be Vietnam Pro giữ vai trò font nội dung, nhưng cặp font tổng thể đã khác vì font tiêu đề đã đổi — đúng tiền lệ Bánh Lăn (đổi font tiêu đề là đủ đổi cặp).
- **Nhiệt màu: TỐI-ẤM — KHÔNG CẦN ĐỔI:** giữ nguyên công thức gợi ý trong yêu cầu (nền tối `#1F1A15`, chữ kem `#F1E7D3`, nhấn vàng đồng da `#C68B4A`). Chuỗi nhiệt sau khi chọn: Da Mộc (tối-ấm) → Kim Ngọc (tối-ấm) → Đắng Ngọt (sáng-ấm): chỉ 2 project tối-ấm liên tiếp, KHÔNG tạo thành 3 project liên tiếp cùng nhiệt màu. Không khí xưởng da buổi tối, ánh đèn vàng, da sẫm được giữ nguyên.
- **Điểm nhấn đặc sắc riêng: "đường chỉ khâu + lỗ đục da"** (xem mục riêng bên dưới) — khác "vạch chia thanh socola" của Đắng Ngọt, "vạch cắt giác + sao 4 cánh" của Kim Ngọc, "vạch hàn + tem cỡ khung" của Bánh Lăn.

## Tổng quan

- Archetype: **A3 Lệch tâm** — bố cục lệch trục, ảnh lớn làm chủ đạo, chữ chồng lấn mép ảnh.
- Ngôn ngữ: tiếng Việt, hỗ trợ dấu đầy đủ (cả Playfair Display và Be Vietnam Pro đều hỗ trợ tiếng Việt).
- Sản phẩm visual-first (§16.1): ưu tiên bố cục ảnh lớn + khoảng trắng — ảnh hero và ảnh bộ sưu tập chiếm diện tích lớn, section cách nhau bằng khoảng trắng rộng, không nhồi chữ.

## Bảng màu (mã hex + vai trò)

| Mã hex | Vai trò |
| `#1F1A15` | Nền chính toàn trang — nâu da sẫm, tối-ấm |
| `#2A211A` | Nền khối phụ xen kẽ (thẻ sản phẩm, khối quy trình) — nâu da nhạt hơn nền chính một nấc |
| `#F1E7D3` | Chữ chính + tiêu đề — kem da thuộc, tương phản cao trên nền tối |
| `#B8A88F` | Chữ phụ (mô tả ngắn, chú thích ảnh, ghi chú giá mẫu) — be xám ấm |
| `#C68B4A` | Nhấn chính — vàng đồng da bò: nút bấm, giá mẫu, đường chỉ khâu, vạch chia |
| `#8A5A2B` | Nhấn phụ — nâu da đậm: viền thẻ, dây tag giá, chân trang; không làm nền khối lớn |

Quy tắc dùng màu: nền luôn là tối (`#1F1A15` hoặc `#2A211A` xen kẽ theo khối); không dùng khối nền sáng toàn trang; màu nhấn `#C68B4A` chỉ dùng cho nút, giá, đường chỉ khâu — không tô nền lớn bằng màu nhấn; tối đa 2 màu nền trong một khối.

## Typography

- Font tiêu đề: **Playfair Display** (serif cổ điển, hỗ trợ tiếng Việt) — hero 64px desktop / 40px mobile, tiêu đề khối 40px desktop / 28px mobile, tên sản phẩm 28px.
- Font nội dung: **Be Vietnam Pro** (hỗ trợ tiếng Việt) — nội dung 17px, dòng cao 1.7; chú thích 14px; nút bấm 16px đậm; nhãn khối 13px đậm, chữ hoa.
- Không dùng thêm font thứ ba.

## Bố cục (A3 Lệch tâm)

- Hero: ảnh thợ khâu tay chiếm 62% chiều ngang, lệch phải; khối tiêu đề ("Da Mộc — Đồ da khâu tay") chồng lấn sang trái lên mép ảnh 12%; nút chính "Xem bộ sưu tập" + nút phụ "Đặt làm riêng".
- Các khối tiếp theo lệch luân phiên: ảnh 55–65% lệch trái rồi lệch phải, khối chữ chồng lên mép ảnh 8–12%; không khối nào căn giữa đều hai bên.
- Khoảng trắng: padding section 96px desktop / 56px mobile; khoảng cách giữa các khối tối thiểu 64px desktop.
- Mobile (dưới 768px): xếp dọc, ảnh trước chữ sau, bỏ chồng lấn (chữ nằm dưới ảnh, không đè lên ảnh); ảnh full chiều ngang.

## Quy tắc hình ảnh (§16.3)

- Ảnh mẫu chất lượng cao, đồng tông ấm, cận cảnh chất liệu da, ánh sáng vàng ấm — đúng tinh thần xưởng thủ công châu Âu cổ điển.
- Tỉ lệ khung: hero 4:3 desktop / 3:2 mobile; ảnh bộ sưu tập 1:1; ảnh quy trình 4:3; ảnh câu chuyện 3:2.
- Ảnh lệch tông lạnh/xanh hoặc mờ thì không dùng. Khi dựng trang, ghi rõ ảnh là ảnh mẫu.

## Khối nội dung (theo thứ tự)

1. Hero — tiêu đề, mô tả ngắn 1 câu, 2 nút.
2. Câu chuyện xưởng — ảnh thợ + đoạn giới thiệu ngắn, lệch trái.
3. Bộ sưu tập — lưới thẻ sản phẩm kèm giá mẫu, mỗi giá ghi rõ "(giá mẫu)"; thẻ có viền chỉ khâu (xem điểm nhấn).
4. Quy trình 4 bước — chọn da → cắt → khâu tay → hoàn thiện; mỗi bước 1 ảnh + 1 dòng mô tả.
5. Cảm nhận khách — 2–3 cảm nhận mẫu, ghi rõ là mẫu.
6. Form đặt làm riêng — chỉ giao diện (không gửi thật), kèm ghi chú "form mẫu".
7. Chân trang — [CẦN BỔ SUNG] địa chỉ, điện thoại, giờ mở cửa, người phụ trách (chờ dữ liệu thật từ PO/khách).

## Điểm nhấn đặc sắc: "đường chỉ khâu + lỗ đục da"

- Vạch chia giữa các khối KHÔNG phải đường kẻ liền: là **đường chỉ khâu** — đường nét đứt (dash 12px, gap 8px) màu `#C68B4A`, dày 2px, hai đầu có **lỗ đục tròn rỗng** đường kính 6px viền `#C68B4A`.
- Thẻ sản phẩm có **viền chỉ khâu**: border nét đứt màu `#C68B4A` inset 10px so với mép thẻ (đường chỉ chạy bên trong thẻ, như mép da khâu tay).
- Thẻ giá hình **tag da**: góc bo 6px, 1 lỗ đục tròn ở góc trên cùng + dây treo vẽ bằng đường mảnh `#8A5A2B` nối từ lỗ ra mép thẻ.
- Không dùng đường kẻ liền làm vạch chia chính ở bất cứ đâu trên trang.

## Ghi chú cho Dev / QA

- Dev dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách; ảnh dùng ảnh mẫu đồng tông ấm, đúng tỉ lệ khung.
- QA đối chiếu bản dựng với tài liệu này ở mức code + thị giác theo §16.4, kèm kiểm tra đa dạng §16.5: archetype A3 phải khác A5 (Đắng Ngọt) và A2 (Kim Ngọc); cặp font Playfair Display + Be Vietnam Pro phải khác nguyên cặp Fraunces + Be Vietnam Pro của Đắng Ngọt.
