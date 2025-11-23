# 📚 Automated Testing with Selenium  
### 🔍 Công cụ kiểm thử tự động cho ứng dụng BookCart  
## 🚀 Giới thiệu Project
Đây là bài tập Assignment 2 của môn **Kiểm Thử Phần Mềm**, tập trung vào việc kiểm thử tự động website **BookCart**:  
🔗 https://bookcart.azurewebsites.net/

Toàn bộ quá trình kiểm thử được thực hiện bằng **Selenium WebDriver + Python**.  
Mục tiêu chính là mô phỏng hành vi người dùng và xác minh các chức năng quan trọng của website hoạt động chính xác.

- Đăng ký tài khoản  
- Đăng nhập / đăng xuất  
- Tìm kiếm sản phẩm  
- Thêm giỏ hàng, wishlist  
- Điều hướng menu  
- Kiểm tra đơn hàng  
- Kiểm thử form và validation  

---

## 🎯 Mục tiêu Kiểm Thử
:contentReference[oaicite:1]{index=1}

- Đảm bảo các tính năng cốt lõi của BookCart hoạt động ổn định.  
- Kiểm tra tính chính xác của các chức năng như login, register, search, cart, wishlist, orders.  
- Phát hiện lỗi tiềm ẩn thông qua automation.  
- Tăng hiệu suất kiểm thử so với manual testing.  

---

## 🛠 Công Nghệ Sử Dụng 
:contentReference[oaicite:2]{index=2}

- **Python**  
- **Selenium WebDriver**  
- **Chrome Browser**  
- **Chromedriver**  
- **PyTest / unittest** 

---
## ✔️ Danh Sách Test Cases
Dưới đây là tổng quan các test case đã thực hiện, trích từ báo cáo (trang 4–29):  
:contentReference[oaicite:3]{index=3}

### 🔐 1. Login / Register
- TC001 – Đăng ký hợp lệ  
- TC002 – Đăng ký sai first name + confirm password không khớp  
- TC003 – Đăng nhập thành công  
- TC004 – Đăng nhập với username sai  
- TC005 – Đăng xuất  

### 🔎 2. Search
- TC006 – Tìm kiếm bằng Enter (Fail)  
- TC007 – Tìm kiếm theo đề xuất (Pass)  
- TC008 – Tìm kiếm theo giá  

### 🛒 3. Cart – Form – Orders
- TC009 – Tìm kiếm đơn hàng trong My Orders  
- TC010 – Register với ký tự số (Fail)  
- TC011 – Register không chọn giới tính (Fail)  
- TC012 – Checkout thiếu thông tin  

### 🧭 4. Navigation
- TC013 – Điều hướng danh mục  
- TC014 – Điều hướng menu sau login  
- TC015 – Xem My Orders + chuyển trang  

### ❤️ 5. Wishlist / Cart
- TC007 (khác) – Thêm sản phẩm từ trang chi tiết  
- TC008 (khác) – Thêm sản phẩm từ trang chính  
- TC011 – Thêm wishlist  
---

1. [Yêu Cầu](#yêu-cầu)
2. [Cài Đặt](#cài-đặt)
3. [Thiết Lập Môi Trường](#thiết-lập-môi-trường)
4. [Chạy Tập Lệnh](#chạy-tập-lệnh)
5. [Khắc Phục Sự Cố](#khắc-phục-sự-cố)

## Yêu Cầu

Trước khi bắt đầu thiết lập, hãy đảm bảo rằng bạn đã cài đặt:

- **Python** (phiên bản 3.7 trở lên): Tải từ [trang chính thức của Python](https://www.python.org/downloads/).
- **Google Chrome**: Các tập lệnh được thiết kế để chạy trên Chrome, nhưng bạn có thể chỉnh sửa để sử dụng trình duyệt khác nếu cần.
- **ChromeDriver**: Cần thiết để Selenium tương tác với Chrome. Tải phiên bản phù hợp với phiên bản Chrome của bạn từ [ChromeDriver downloads](https://sites.google.com/chromium.org/driver/).

> **Lưu ý**: Bạn cũng có thể sử dụng các driver khác (như GeckoDriver cho Firefox), nhưng cần chỉnh sửa thiết lập phù hợp.

## Cài Đặt

1. **Clone kho lưu trữ**:
   ```bash
   git clone https://github.com/caarotnee/N8_VoKhanhLinh_Assignment2.git
   cd N8_VoKhanhLinh_Assignment2
   ```

2. **Tạo môi trường ảo** (khuyên dùng):
   ```bash
   python -m venv venv
   ```

3. **Kích hoạt môi trường ảo**:
   - Trên Windows:
     ```bash
     .\venv\Scripts\activate
     ```
   - Trên macOS và Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Cài đặt các gói yêu cầu**:
   - Cài đặt các thư viện cần thiết từ file `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

## Thiết Lập Môi Trường

1. **Tải và thiết lập ChromeDriver**:
   - Tải ChromeDriver và đặt trong thư mục của dự án.
   - Thêm ChromeDriver vào PATH hoặc chỉ định đường dẫn trong mã của bạn.

2. **Cấu hình biến môi trường (nếu cần)**:
   - Nếu các tập lệnh yêu cầu API key hoặc thông tin đăng nhập, hãy tạo file `.env` trong thư mục dự án và khai báo biến của bạn:
     ```plaintext
     API_KEY=your_api_key
     ```

## Chạy Tập Lệnh

1. **Đảm bảo môi trường ảo đang hoạt động**:
   ```bash
   source venv/bin/activate  # Hoặc .\venv\Scripts\activate trên Windows
   ```

2. **Chạy tập lệnh**:
   - Chạy một tập lệnh bằng Python:
     ```bash
     python path/to/your_script.py
     ```
   - Bạn cũng có thể chạy trực tiếp các kiểm thử nếu sử dụng `unittest` hoặc `pytest`:
     ```bash
     pytest path/to/tests/
     ```

3. **Chế độ Headless (không giao diện)**:
   - Để chạy kiểm thử ở chế độ không giao diện, hãy điều chỉnh tùy chọn của Chrome trong phần thiết lập Selenium:
     ```python
     from selenium import webdriver
     from selenium.webdriver.chrome.options import Options

     options = Options()
     options.add_argument("--headless")
     driver = webdriver.Chrome(options=options)
     ```

## Khắc Phục Sự Cố

- **Vấn Đề Phiên Bản ChromeDriver**: Đảm bảo phiên bản ChromeDriver phù hợp với phiên bản Chrome của bạn.
- **Lỗi Quyền Truy Cập**: Nếu gặp lỗi quyền trên macOS/Linux, bạn có thể cần thay đổi quyền của ChromeDriver:
  ```bash
  chmod +x path/to/chromedriver
  ```

## License

Dự án này được cấp phép theo giấy phép MIT - xem file `LICENSE` để biết thêm chi tiết.
