# Rủi ro mật khẩu mặc định trên thiết bị IoT (Default Password Risk in IoT Devices)

## Giới thiệu

Đây là repository phục vụ đề tài nghiên cứu:

**Rủi ro mật khẩu mặc định trên thiết bị IoT**

Đề tài được thực hiện trong học phần **Công nghệ Tường lửa và Bảo vệ mạng ngoại vi**, với mục tiêu nghiên cứu các rủi ro bảo mật phát sinh khi thiết bị Internet of Things (IoT) vẫn sử dụng tài khoản và mật khẩu mặc định, đồng thời đề xuất các biện pháp giảm thiểu theo các khuyến nghị của OWASP.

Môi trường nghiên cứu sử dụng **OWASP IoTGoat** kết hợp với **Docker Desktop** để mô phỏng các tình huống bảo mật trong phạm vi học tập.

---

# Mục tiêu nghiên cứu

Đề tài hướng đến các mục tiêu sau:

- Phân tích nguyên nhân hình thành lỗ hổng mật khẩu mặc định trên thiết bị IoT.
- Phân tích các tình huống khai thác liên quan đến:
  - Default Password
  - Shared Password
  - Hard-coded Credential
  - Không giới hạn số lần đăng nhập sai
- Xây dựng mô hình Threat Modeling bằng DFD, Attack Tree và STRIDE.
- Đánh giá rủi ro bằng Risk Matrix.
- Đề xuất Checklist chính sách mật khẩu và các biện pháp giảm thiểu.

---

# Môi trường thực hiện

| Thành phần | Phiên bản |
|------------|-----------|
| Windows | 11 24H2 |
| Docker Desktop | 28.x |
| OWASP IoTGoat | Latest |
| Git | 2.x |
| GitHub | Cloud |
| Draw.io | Online |
| Microsoft Word | Microsoft 365 |

---

# Các tình huống nghiên cứu

Đề tài tập trung đánh giá bốn tình huống phổ biến.

| Mã | Nội dung |
|-----|-------------------------------|
| TC-01 | Kiểm tra tài khoản mặc định |
| TC-02 | Kiểm tra thay đổi mật khẩu |
| TC-03 | Kiểm tra Brute Force |
| TC-04 | Kiểm tra Hard-coded Credential |

---

# Công nghệ sử dụng

- Docker Desktop
- OWASP IoTGoat
- SSH
- Git
- GitHub
- Draw.io
- Microsoft Word

---

# Cấu trúc Repository

```text
iot-default-password-risk/
│
├── README.md
│
├── report/
│   ├── BaoCao.docx
│   └── BaoCao.pdf
│
├── slides/
│   ├── BaoCao.pptx
│   └── BaoCao.pdf
│
├── configs/
│   └── docker_run.txt
│
├── src/
│   └── run_lab.txt
│
├── data/
│   └── test_cases.xlsx
│
├── results/
│   ├── screenshots/
│   └── logs/
│
└── references/
    └── references.md
```

---

# Hướng dẫn triển khai

## 1. Pull Image

```bash
docker pull iotgoat-qemu-iotgoat:latest
```

## 2. Khởi động IoTGoat

```bash
docker run -d \
--name iotgoat \
-p 8080:8080 \
-p 4443:4443 \
-p 2222:2222 \
iotgoat-qemu-iotgoat:latest
```

## 3. Kiểm tra Container

```bash
docker ps
```

## 4. Truy cập Web

```
http://localhost:8080
```

hoặc

```
https://localhost:4443
```

## 5. SSH

```bash
ssh root@localhost -p 2222
```

---

# Kết quả đạt được

Đề tài đã thực hiện:

- Phân tích tài khoản mặc định.
- Phân tích Hard-coded Credential.
- Đánh giá nguy cơ Brute Force.
- Xây dựng Data Flow Diagram.
- Xây dựng Attack Tree.
- Xây dựng STRIDE.
- Xây dựng Asset Inventory.
- Xây dựng Risk Matrix.
- Đề xuất Checklist chính sách mật khẩu.
- Đối chiếu với OWASP IoT Top 10 và OWASP ISVS.

---

# Tài liệu tham khảo

1. OWASP Internet of Things Project

https://owasp.org/www-project-internet-of-things/

2. OWASP IoTGoat

https://github.com/OWASP/IoTGoat

3. OWASP IoT Security Testing Guide (ISTG)

https://owasp.org/www-project-istg/

4. William Stallings.
Network Security Essentials: Applications and Standards.
7th Edition.

5. William Stallings.
Cryptography and Network Security: Principles and Practice.
8th Edition.

---

# Thành viên thực hiện

**Họ và tên:** Huỳnh Bùi Hoàng Ân

**Chuyên ngành:** An toàn thông tin

**Trường:** (Điền tên trường)

---

# Giấy phép

Repository được xây dựng phục vụ mục đích học tập và nghiên cứu.

Không sử dụng các nội dung trong repository này để khai thác trái phép các hệ thống thông tin hoặc thiết bị IoT ngoài phạm vi được cho phép.
