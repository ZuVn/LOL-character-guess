# LOL Character Guess

Game đoán tướng Liên Minh Huyền Thoại kiểu Loldle (chế độ Classic). Mỗi lần đoán sẽ so sánh từng thuộc tính của tướng bạn chọn với tướng đáp án, rồi dựa vào màu gợi ý để đoán tiếp.

Toàn bộ chỉ có HTML/JS thuần, không cần build, không cần server.

## Chạy

- Vào trang https://zuvn.github.io/LOL-character-guess/ để chơi ngay

- Mở thẳng `index.html` bằng trình duyệt, hoặc
- Chạy server tĩnh: `python3 -m http.server` rồi vào http://localhost:8000

## Cách chơi

1. Gõ tên tướng vào ô nhập, chọn trong danh sách gợi ý (Enter sẽ chọn gợi ý đầu tiên).
2. Mỗi lượt đoán thêm một hàng vào bảng, mỗi ô là một thuộc tính:

   | Thuộc tính | Ý nghĩa |
   |---|---|
   | Gender | Giới tính |
   | Position(s) | Vị trí đi đường |
   | Species | Chủng tộc |
   | Resource | Loại tài nguyên (Mana, Energy, Manaless, ...) |
   | Range type | Cận chiến / Đánh xa |
   | Region(s) | Vùng đất |
   | Release year | Năm ra mắt |

3. Màu ô:
   - 🟩 **Xanh**: trùng khớp hoàn toàn
   - 🟨 **Vàng**: trùng một phần (ví dụ cùng có một vị trí/vùng đất nhưng không đủ hết)
   - 🟥 **Đỏ**: sai hoàn toàn
   - Với **Release year**: mũi tên ↑ nghĩa là tướng đáp án ra mắt muộn hơn, ↓ là sớm hơn.
4. Đoán trúng để thắng. Không đoán được thì bấm **Give up** để xem đáp án.

## Các nút

- **Ngày (date picker)**: chơi lại đề của một ngày bất kỳ trong quá khứ. Mỗi ngày có một tướng cố định, ai chơi cùng ngày cũng cùng đáp án.
- **Today**: quay về đề hôm nay.
- **🎲 Random**: chơi một ván ngẫu nhiên.
- **📋 Share result**: copy kết quả dạng ô màu để khoe với bạn bè.

Số trận thắng và chuỗi thắng (Streak) được lưu trong trình duyệt (localStorage).

## Cấu trúc

- `index.html` — giao diện và logic game
- `data.js` — dữ liệu thuộc tính của các tướng
- `img/Champion/` — ảnh icon tướng

Thêm/sửa tướng: chỉnh mục tương ứng trong `data.js` (trường `name`, `icon`, `attrs`).
