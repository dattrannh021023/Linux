# Cài wordpress trên 02 máy gồm: một máy DB, một máy WEB

Để cài WordPress trên hai máy tính khác nhau - một máy chủ cơ sở dữ liệu (DB) và một máy chủ web (WEB), bạn sẽ cần thực hiện các bước sau:

1. **Cài đặt máy chủ cơ sở dữ liệu (DB)**:
    - **Bước 1**: Cài đặt và cấu hình một hệ thống quản lý cơ sở dữ liệu (DBMS) như MySQL hoặc MariaDB trên máy chủ DB. Sử dụng giao diện dòng lệnh hoặc công cụ quản trị DB như phpMyAdmin để tạo một cơ sở dữ liệu mới và người dùng cơ sở dữ liệu cho WordPress.
    - **Bước 2**: Chắc chắn rằng máy chủ DB có một địa chỉ IP hoặc tên miền mà máy chủ web có thể truy cập.
2. **Cài đặt máy chủ web (WEB)**:
    - **Bước 1**: Cài đặt một máy chủ web như Apache hoặc Nginx trên máy chủ WEB. Đảm bảo máy chủ web đã hoạt động và có quyền truy cập internet.
    - **Bước 2**: Tải và cài đặt WordPress trên máy chủ WEB. Bạn có thể tải phiên bản mới nhất của WordPress từ trang web chính thức của họ và giải nén tệp zip. Sau đó, chuyển nó đến thư mục gốc của máy chủ web (thường là `/var/www/html` trên Linux).
    - **Bước 3**: Cấu hình WordPress để sử dụng cơ sở dữ liệu mà bạn đã tạo trên máy chủ DB. Để làm điều này, bạn cần chỉnh sửa tệp cấu hình `wp-config.php` trong thư mục gốc của WordPress trên máy chủ WEB. Cung cấp thông tin về cơ sở dữ liệu (tên cơ sở dữ liệu, người dùng, mật khẩu và địa chỉ máy chủ DB).
    - **Bước 4**: Sau khi cấu hình xong, bạn có thể truy cập trình cài đặt WordPress bằng cách truy cập trình duyệt web và điền địa chỉ IP hoặc tên miền của máy chủ WEB. Bạn sẽ được hướng dẫn để hoàn thiện quá trình cài đặt WordPress.
3. **Cài đặt cả hai máy**:
    - Đảm bảo rằng máy chủ DB có khả năng kết nối từ xa từ máy chủ WEB. Điều này có nghĩa là cấu hình máy chủ DB để cho phép kết nối từ máy chủ WEB bằng cách mở cổng truy cập cho DBMS và xác thực. Điều này có thể được thực hiện trong cấu hình DBMS của bạn.

Lưu ý rằng việc cài đặt và cấu hình máy chủ cơ sở dữ liệu có thể phức tạp hơn và yêu cầu sự am hiểu về quản trị cơ sở dữ liệu. Hãy đảm bảo rằng bạn đã thực hiện các biện pháp bảo mật cần thiết để bảo vệ cả hai máy.