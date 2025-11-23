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

- Đảm bảo các tính năng cốt lõi của BookCart hoạt động ổn định.  
- Kiểm tra tính chính xác của các chức năng như login, register, search, cart, wishlist, orders.  
- Phát hiện lỗi tiềm ẩn thông qua automation.  
- Tăng hiệu suất kiểm thử so với manual testing.  

---

## 🛠 Công Nghệ Sử Dụng 

- **Python**  
- **Selenium WebDriver**  
- **Chrome Browser**  
- **Chromedriver**  
- **PyTest / unittest** 

---
## 📌 TEST CASE LIST (Full)

### 1️⃣ LOGIN — REGISTER — LOGOUT

#### ✔ Register
- **TC001 – Register (Valid)**  
  Đăng ký tài khoản hợp lệ → chuyển sang trang Login.

- **TC002 – Register (Invalid: First name trống + Confirm password không khớp)**  
  Lỗi: “First Name is required”, “Password do not match”.

- **TC003 – Register (Invalid: Firstname/Lastname là ký tự số)**  
  Hệ thống báo lỗi validation.

- **TC004 – Register (Invalid: Không chọn giới tính)**  
  Lỗi: “please select your gender”.

- **TC005 – Register (Invalid: Username đã tồn tại)**  
  Lỗi: “User Name is not available”.

#### ✔ Login
- **TC006 – Login (Valid)**  
  Đăng nhập thành công → về trang Home.

- **TC007 – Login (Invalid username)**  
  Lỗi: “Username or Password is incorrect”.

- **TC008 – Login (Blank fields)**  
  Lỗi *mat-error* khi để trống.

#### ✔ Logout
- **TC009 – Logout Successfully**  
  Logout → quay về trang Login.


---

### 2️⃣ FORM VALIDATION
- **TC010 – Checkout với form trống**  
  Các trường hiển thị class *mat-form-field-invalid*.

- **TC011 – Checkout với pincode 2 chữ số**  
  Lỗi: “pincode must have 6 digits only and cannot start with 0”.

---

### 3️⃣ NAVIGATION
- **TC012 – Navigate Categories**  
  Điều hướng giữa: Biography, Fiction, Mystery, Fantasy, Romance, All Categories.

- **TC013 – Navigation User Menu**  
  Wishlist → Cart → My Orders → Swagger → GitHub → Logout.

- **TC014 – Navigate My Orders Pagination**  
  Chọn order → Next Page → duyệt đến hết.

---

### 4️⃣ ORDER SEARCH
- **TC015 – Search My Orders**  
  Tìm bằng Order ID → hiển thị đúng kết quả.

---

### 5️⃣ SEARCH FUNCTION
- **TC016 – Search by Enter (Known Issue)**  
  Tìm bằng Enter với chuỗi dài → kết quả có thể không hiển thị.

- **TC017 – Search using Suggestion Dropdown**  
  Nhập “slayer” → chọn gợi ý → hiển thị đúng sách.

- **TC018 – Filter by Price**  
  Slider giá = 311 → tất cả sản phẩm ≤ 311.

---

### 6️⃣ WISHLIST
- **TC019 – Add 1 Product to Wishlist**  
  Sản phẩm hiển thị trong wishlist.

---

### 7️⃣ CART — CHECKOUT

#### ✔ Add to Cart
- **TC020 – Add Product by ID (15)**  
  Giỏ hàng hiển thị “Harry Potter and the Sorcerer's Stone”.

- **TC021 – Add Two Products from Homepage**  
  Cả 2 sản phẩm hiển thị trong cart.

- **TC022 – View Cart**  
  Giỏ hàng có “All of Us with Wings”.

#### ✔ Cart Operations
- **TC023 – Cart Total Calculation**  
  Tổng giá = price × quantity.

- **TC024 – Clear Cart**  
  Hiển thị: “Your shopping cart is empty.”

- **TC025 – Adjust Product Quantity**  
  Tăng đến 5 → giảm 4 → hiển thị đúng.

#### ✔ Checkout
- **TC026 – Checkout Successfully**  
  Điền đầy đủ thông tin → tạo order → chuyển sang My Orders.

- **TC027 – Checkout without Login**  
  Nhấn checkout khi chưa login → tự động chuyển sang trang Login.

---

### 8️⃣ RESPONSIVE TESTING
- **TC028 – Responsive iPhone (375×667)**
- **TC029 – Responsive iPad (768×1024)**
- **TC030 – Responsive Tablet (1280×800)**
- **TC031 – Responsive Desktop (1920×1080)**

Kiểm tra: logo, navbar, menu mobile, liên kết Swagger/GitHub, giao diện từng thiết bị.

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
