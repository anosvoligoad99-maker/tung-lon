# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:Le Minh Quan**
- **Lớp:HN-KS26-CNTT03**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Recuse -Force
mv
mv .\tai_lieu_ban_giao.txt .\docs\
mkdir backup
cp .\data\chi_phi_model_thang_11.xlsx .\backup\
rm .\model_cache_01.tmp
 cd .\logs\
 ls
  cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
 Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-r---        11/10/2026   1:48 PM                backup
d-r---        11/10/2026   1:44 PM                data
d-r---        11/10/2026   1:47 PM                docs
d-r---        11/10/2026   1:44 PM                evidence
d-r---        11/10/2026   1:44 PM                logs
d-r---        11/10/2026   1:41 PM                web
-a----        11/10/2026   1:41 PM             96 .env
-a----        11/10/2026   1:41 PM           2665 bai_lam.md


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM           5815 chi_phi_model_thang_11.xl
                                                  sx


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM           5815 chi_phi_model_thang_11.xl
                                                  sx


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM            204 tai_lieu_ban_giao.txt


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM           1234 inference.log


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-r---        11/10/2026   1:41 PM                images
-a----        11/10/2026   1:41 PM            644 app.js
-a----        11/10/2026   1:41 PM            567 index.html
-a----        11/10/2026   1:41 PM            460 style.css


    Directory: D:\MiniPrjoect\starter-kit\quan-ly-model-ai\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/10/2026   1:41 PM            339 logo-ai-hub.png
```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```shell
Get-Content .\logs\inference.log | Select-String "ERROR" >> .\logs\loi_model.txt

```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3

```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
(Get-Content .\logs\inference.log | Select-String "WARNING").Count
```

```text
5
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```shell
=== BAO CAO VAN HANH MODEL AI ===

2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3
2026-11-10 08:42:15 ERROR POST /v1/chat/completions model=DEEPSEEK-R1
2026-11-10 08:49:51 ERROR POST /v1/images/generations model=FLUX-PRO
2026-11-10 08:53:33 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 09:05:27 ERROR POST /v1/embeddings model=MISTRAL-L




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 
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
| 1   |   network                         |     network.png                        |                |
| 2   | console                           |  console.png                           |                |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:**
- **Expected:**
- **Actual:**
- **Log:**

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
