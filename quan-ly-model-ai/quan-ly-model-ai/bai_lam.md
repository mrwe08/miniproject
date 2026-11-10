# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:Nguyễn Thế Huy**
- **Lớp:**
- **Link repository:https://github.com/mrwe08/miniproject**
- **Hệ điều hành (Windows/macOS):macOS**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```bash
pwd
ls -a
mv tai_lieu_ban_giao.txt docs
mkdir backup
cp data/chi_phi_model_thang_11.xlsx backup
rm model_cache_01.tmp
cd logs
ls -a
cd ..


```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
.		.DS_Store	backup		docs		logs
..		.env		data		evidence	web

./backup:
.				chi_phi_model_thang_11.xlsx
..

./data:
.				chi_phi_model_thang_11.xlsx
..

./docs:
.			..			tai_lieu_ban_giao.txt

./evidence:
.	..

./logs:
.		..		inference.log

./web:
.		app.js		index.html
..		images		style.css

./web/images:
.		..		logo-ai-hub.png

```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```bash
cat logs/inference.log|grep "ERROR" > logs/loi_model.txt
head -2 logs/loi_model.txt

```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3

```

### b) Lệnh đếm số dòng WARNING và kết quả

```bash
cat logs/inference.log|grep "WARNING"|wc -l

```

```text
       5

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```bash
./tong_hop.sh

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO VAN HANH MODEL AI ===
2026-11-10 08:09:18 WARNING POST /v1/embeddings model=LLAMA-2-OLD
2026-11-10 08:16:05 WARNING GET /v1/fine-tune/jobs-legacy
2026-11-10 08:38:29 WARNING GET /images/model-card-v1.png
2026-11-10 09:01:44 WARNING POST /v1/completions model=DAVINCI-002
2026-11-10 09:14:02 WARNING GET /v1/quota/expired-key
       6


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |Network                            |logo.png                             |                |sửa lại đường dẫn logo
| 2   |console                            |Uncaught ReferenceError: hienThiBangModel is not defined                             |sửa lại tên hienThiBangModel thành hienThiBangModelAI                |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Tôi là sinh viên năm nhất chưa fix lỗi hiển thị dữ liệu của web bao giờ
- **Expected:** Bây giờ trang web xem phim của tôi muốn có đủ dữ liệu ở bảng hiển thị giao diện 
- **Actual:** Dữ liệu trên trang web không có gì và tôi vào tab console thấy thông báo lỗi app.js:18 Uncaught ReferenceError: hienThiBangGiaModel is not
- **Log:** app.js:18 Uncaught ReferenceError: hienThiBangGiaModel is not

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
