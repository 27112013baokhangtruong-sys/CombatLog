# CombatLog

Plugin chống combat log cho server **Paper 26.3** (Java 25). Người chơi bị gắn trạng thái chiến đấu khi giao tranh, và bị phạt nếu thoát game giữa trận.

## Tính năng

- Đếm ngược thời gian combat bằng **BossBar** hoặc **ActionBar**
- Phạt người thoát game khi đang combat (chạy lệnh tùy chỉnh như tempban, hoặc giết người chơi)
- Không phạt khi người chơi bị kick
- Chặn dịch chuyển (lệnh, plugin, chorus fruit), Mending, Riptide, Elytra, mỗi mục bật/tắt riêng
- Chặn lệnh theo blacklist hoặc whitelist, tự nhận cả alias và dạng `plugin:lệnh`
- Gắn combat khi bị nổ hoặc khi Ender Pearl tiếp đất
- Tự gỡ combat khi giết đối thủ
- Bỏ qua các thế giới chỉ định (ví dụ `ffa`)
- Toàn bộ tin nhắn chỉnh được trong `messages.yml`

## Chưa hỗ trợ (bản 1.0.0)

Các mục sau đã có sẵn trong `config.yml` nhưng chưa có code xử lý:

- Tích hợp WorldGuard (rào chắn vùng an toàn, chống kill abuse)
- Vùng chiến đấu (`combat-zone`)
- Hiệu ứng thuốc khi bị gắn combat (`tag-effects`)
- `restrictions.punishment.damage`

## Yêu cầu

- Java 25
- Paper 26.3
- EssentialsX (chỉ khi dùng lệnh `essentials:tempban` trong config)

## Cài đặt

1. Tải file `.jar` ở mục **Releases** (hoặc tự build bên dưới).
2. Bỏ vào thư mục `plugins/` của server.
3. Khởi động lại server để tạo `config.yml` và `messages.yml`.
4. Chỉnh file cấu hình rồi dùng `/combatlog reload`.

## Lệnh

| Lệnh | Mô tả |
|------|-------|
| `/combatlog reload` | Tải lại cấu hình và tin nhắn |
| `/combatlog status [người chơi]` | Xem trạng thái chiến đấu |
| `/combatlog untag [người chơi]` | Gỡ trạng thái chiến đấu |

Alias: `/combat`.

## Quyền

| Quyền | Mặc định | Mô tả |
|-------|----------|-------|
| `combatlog.admin` | op | Dùng các lệnh `/combatlog` |
| `combatlog.bypass` | không ai | Không bị gắn trạng thái chiến đấu |

## Cấu hình

- `combat-log.timer`: thời gian và kiểu hiển thị
- `combat-log.restrictions`: các giới hạn khi combat
- `combat-log.logout`: hình phạt khi thoát game (`mode: commands` hoặc `mode: kill`)
- `combat-log.triggers`: điều kiện gắn combat
- `combat-log.command-restrictions`: danh sách lệnh bị chặn
- `combat-log.ignored-worlds`: thế giới không áp dụng

Trong `messages.yml`, phần `combat-log.messages` dùng mã màu `&`, phần `commands` dùng MiniMessage.

Placeholder: `{player}`, `{timeLeft}`, `{maxTime}`, `{label}`, `{world}`, `{gamemode}`, `{value}`.

## Build từ mã nguồn

Cần JDK 25 và Maven:

```bash
mvn clean package
```

File `.jar` nằm trong `target/CombatLog-1.0.0.jar`.

Nếu Maven không tìm thấy `paper-api`, đổi `paper.version` trong `pom.xml` sang một build có trong
[repo Paper](https://repo.papermc.io/service/rest/repository/browse/maven-public/io/papermc/paper/paper-api/).

## Đóng góp

Pull request và issue đều được hoan nghênh. Vui lòng ghi rõ phiên bản server và các bước tái hiện lỗi.

## Giấy phép

MIT, xem file [LICENSE](LICENSE).
