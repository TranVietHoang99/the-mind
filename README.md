# 🧠 The Mind

Game hợp tác **The Mind** (Wolfgang Warsch, 2018) cho 2–4 người, chơi ngay trên trình duyệt: cả đội đánh các lá 1–100 lên bàn theo thứ tự tăng dần, không được nói chuyện và không có lượt.

Chơi online: https://tranviethoang99.github.io/the-mind/

## Chế độ chơi
- **Chơi với máy**: nhập tên, chọn số máy (1–3) và nhịp đếm của máy (Chậm/Vừa/Nhanh), bấm *Chơi với máy*.
- **Online 2–4 người**: bấm *Tạo phòng*, gửi mã hoặc link cho bạn bè; bạn bè nhập mã và bấm *Vào phòng*.
  Chủ phòng có thể *+ Thêm máy* vào ghế trống, rồi bấm *Bắt đầu*.
  Người tạo phòng phải **giữ tab mở**, vì máy chủ phòng giữ trạng thái ván chơi. Khách rớt mạng có thể vào lại (cùng tab).

## Luật tóm tắt
- Cấp N: mỗi người N lá. Số cấp: 2 người 12, 3 người 10, 4 người 8. Vượt qua cấp cuối là thắng.
- Không có lượt: ai thấy đến lúc thì đánh lá thấp nhất của mình. Không được nói hay ra hiệu về bài.
- Đầu mỗi cấp và sau mỗi lần đánh sai, cả đội **tập trung**: ai cũng bấm *Sẵn sàng* thì mới chơi. Ai cũng có thể bấm *Dừng lại* để cả đội tập trung lại.
- Đánh một lá khi người khác còn lá nhỏ hơn → mất 1 mạng, mọi lá nhỏ hơn bị loại. Mạng ban đầu = số người; hết mạng là thua.
- **Phi tiêu**: một người đề nghị, cả đội đồng ý thì mỗi người bỏ lá thấp nhất. Bắt đầu với 1 phi tiêu.
- Thưởng: xong cấp 2, 5, 8 → +1 phi tiêu; xong cấp 3, 6, 9 → +1 mạng (tối đa 5 mạng, 3 phi tiêu).

## Cách bấm
- Lá sáng viền trắng là lá thấp nhất của bạn: bấm vào lá hoặc nút *Đánh lá…*.
- Phím Space: đánh lá thấp nhất · Enter: sẵn sàng · Y/N: biểu quyết phi tiêu.
- 🎵 nhạc nền ambient · 🔔 bật/tắt âm thanh (lá càng lớn tiếng càng cao).

## Kỹ thuật
Một file `index.html` duy nhất. Kết nối P2P bằng [PeerJS](https://peerjs.com/), cùng khung với Can't Stop (tối đa 4 người). Chủ phòng chỉ gửi cho mỗi người bài của chính họ.
Máy "đếm thầm" từ lá trên cùng tới lá thấp nhất của mình với nhịp cố định (sai số ±10%), và học dần nhịp đánh của người chơi để đồng bộ.
Chạy thử: `npx http-server the-mind -p 5188`.
