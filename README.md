# HUE HERITAGE MUSIC 🎶

> Ứng dụng AI bảo tồn và lan tỏa di sản âm nhạc Huế — nghe, học hát, phân tích,
> chuyển âm và sáng tạo trên mọi nền tảng.

![Phiên bản](https://img.shields.io/badge/phi%C3%AAn%20b%E1%BA%A3n-0.0.3-blue)
![Nền tảng](https://img.shields.io/badge/n%E1%BB%81n%20t%E1%BA%A3ng-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20Android%20%7C%20Web-orange)

## Giới thiệu

HUE HERITAGE MUSIC là ứng dụng dành cho âm nhạc truyền thống đất cố đô: Nhã nhạc
cung đình, Ca Huế, và các nhạc cụ đặc trưng như đàn nguyệt, kèn bóp, trống chiến,
phách… Phần AI sinh nhạc của hệ thống được huấn luyện riêng trên kho tư liệu âm nhạc
Huế, hướng tới việc gìn giữ âm sắc mộc và kỹ thuật chơi đàn của các nghệ nhân.

Ứng dụng là phần client — kết nối tới máy chủ HUE HERITAGE MUSIC để đăng nhập,
xử lý và lưu trữ.

## Tính năng chính

- 🏛️ **Thư viện di sản** — nghe và duyệt kho nhạc Huế theo thể loại.
- 🎤 **Học hát** — luyện tập theo bài, ghi âm giọng hát, hệ thống so sánh độ chuẩn
  cao độ và nhịp với bản mẫu, theo dõi tiến độ.
- 🎼 **Chuyển âm** — chuyển bản thu thành nốt nhạc (MIDI) phục vụ học tập và nghiên cứu.
- 📊 **Phân tích âm học** — phổ tần, năng lượng, các chỉ số âm học của bản thu.
- 🎹 **Sáng tạo với AI** — sinh giai điệu mới mang phong cách âm nhạc Huế.
- 🔧 **Phục hồi** — xử lý, cải thiện chất lượng bản thu.
- 👤 **Tài khoản & lịch sử** — đăng nhập an toàn (token lưu trong Keychain /
  Credential Manager của hệ điều hành), lịch sử hoạt động cá nhân.

## Tải xuống

Tải bản phát hành mới nhất tại trang
[**Releases**](https://github.com/ghitatruongle/hue-heritage-music-app/releases).

| File | Dành cho |
|---|---|
| `hue-heritage-music-windows.zip` | Windows 10 trở lên |
| `hue-heritage-music-macos.zip` | macOS 12 trở lên (Apple Silicon) |
| `hue-heritage-music-linux.zip` | Linux x64 |
| `hue-heritage-music-android.apk` | Android (cài trực tiếp file APK) |
| `hue-heritage-music-web.zip` | Chạy trong trình duyệt |

## Hướng dẫn cài đặt

### Windows

1. Giải nén file zip vào thư mục tùy ý.
2. Mở `hue_heritage_music.exe`. Nếu Windows SmartScreen hiện cảnh báo: bấm
   **More info → Run anyway** (bản phát hành chưa ký chứng chỉ số).
3. Lần chạy đầu, cho phép truy cập mạng khi Windows Firewall hỏi.

### macOS

1. Giải nén, kéo `hue_heritage_music.app` vào thư mục **Applications**.
2. Lần mở đầu: **chuột phải vào app → Open → Open** (bản build ad-hoc, chưa
   notarize). Từ lần sau mở bình thường bằng double-click.
3. Nếu macOS báo "app damaged / unverified developer", chạy trong Terminal:
   `xattr -cr /Applications/hue_heritage_music.app`

### Linux

1. Giải nén file zip.
2. Cấp quyền chạy và mở file thực thi trong thư mục `bundle`:
   ```bash
   chmod +x hue_heritage_music
   ./hue_heritage_music
   ```
3. Yêu cầu hệ thống: `libgtk-3`, `libsecret` (lưu phiên đăng nhập):
   ```bash
   sudo apt install libgtk-3-0 libsecret-1-0
   ```

### Android

1. Tải file `.apk` về máy, mở trực tiếp để cài đặt.
2. Nếu Android chặn: cho phép **Cài đặt ứng dụng không rõ nguồn gốc** cho trình
   duyệt/quản lý file, rồi mở lại file `.apk`.

### Bản Web

1. Giải nén `hue-heritage-music-web.zip`.
2. Phục vụ bằng một máy chủ web tĩnh, ví dụ:
   ```bash
   cd thu-muc-giai-nen
   python -m http.server 8090
   ```
3. Mở `http://localhost:8090` trong trình duyệt.

## Kết nối máy chủ & đăng nhập

- **Lần chạy đầu**, hộp thoại "Kết nối máy chủ" tự hiện — nhập địa chỉ máy chủ
  do quản trị viên cung cấp, dạng `http://<dia-chi-may-chu>:8000`.
- Có thể đặt sẵn file `GHITA_API.json` cạnh file chạy app với nội dung:
  ```json
  { "server_url": "http://<dia-chi-may-chu>:8000" }
  ```
- **Tài khoản** do quản trị viên hệ thống cấp phát. Liên hệ chủ dự án để được
  cấp tài khoản hoặc mã mời tham gia.
- Phiên đăng nhập được lưu an toàn trong kho hệ điều hành (macOS Keychain,
  Windows Credential Manager, Linux libsecret).

## Sự cố thường gặp

| Hiện tượng | Cách xử lý |
|---|---|
| Windows chặn mở app (SmartScreen) | More info → Run anyway |
| macOS báo "damaged" | `xattr -cr /Applications/hue_heritage_music.app` |
| Không kết nối được máy chủ | Kiểm tra đúng địa chỉ, cùng mạng với máy chủ, firewall cho phép |
| Linux không lưu được đăng nhập | Cài `libsecret-1-0` và keyring của hệ thống |

## Bản quyền

© 2026 ghitatruongle — All rights reserved. Mã nguồn không được công khai.

---

### English (summary)

HUE HERITAGE MUSIC is an AI-assisted app for preserving and spreading the traditional
music of Huế, Vietnam — Nhã nhạc court music, Ca Huế singing, and instruments such as
the đàn nguyệt (moon lute). It offers heritage listening, singing practice with pitch
feedback, transcription, audio analysis, and AI music generation in Huế style.
Download the latest release from the
[**Releases**](https://github.com/ghitatruongle/hue-heritage-music-app/releases) page.
The app connects to a HUE HERITAGE MUSIC server (address provided by the administrator).
© 2026 ghitatruongle — All rights reserved.
