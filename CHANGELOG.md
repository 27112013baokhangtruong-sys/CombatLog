# Changelog

Định dạng theo [Keep a Changelog](https://keepachangelog.com/vi/1.1.0/).

## [1.0.0]

### Thêm
- Gắn combat khi đánh nhau (người đánh, nạn nhân hoặc cả hai), khi bị nổ, khi Ender Pearl tiếp đất
- Đồng hồ đếm ngược bằng BossBar hoặc ActionBar
- Phạt khi thoát game giữa trận: chạy lệnh tùy chỉnh hoặc giết người chơi; không phạt khi bị kick
- Chặn dịch chuyển, Mending, Riptide, Elytra, lệnh (blacklist/whitelist, tự nhận alias)
- Tự gỡ combat khi giết đối thủ
- Bỏ qua thế giới chỉ định
- Lệnh `/combatlog reload|status|untag` kèm tab-complete
- Quyền `combatlog.admin` và `combatlog.bypass`
- `messages.yml` có thể chỉnh toàn bộ tin nhắn

### Chưa hỗ trợ
- Tích hợp WorldGuard, vùng chiến đấu, hiệu ứng thuốc khi bị gắn combat, `punishment.damage`
