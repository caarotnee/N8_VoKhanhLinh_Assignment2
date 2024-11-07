
# N8_VoKhanhLinh_Assignment2

Kho lưu trữ này chứa các tập lệnh Selenium để tự động hóa các quy trình kiểm thử. Làm theo hướng dẫn dưới đây để thiết lập môi trường và chạy các tập lệnh.

## Mục Lục
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
