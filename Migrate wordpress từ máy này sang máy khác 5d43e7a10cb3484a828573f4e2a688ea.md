# Migrate wordpress từ máy này sang máy khác.

Để di chuyển hoặc migrate một trang web WordPress từ một máy chủ sang máy chủ khác, bạn cần thực hiện các bước sau:

**Bước 1: Backup trang web WordPress gốc**

Trước khi bắt đầu, hãy đảm bảo sao lưu toàn bộ trang web WordPress gốc, bao gồm cả cơ sở dữ liệu và tệp tin. Cách bạn sao lưu phụ thuộc vào các công cụ và dịch vụ bạn đang sử dụng, nhưng bạn có thể sử dụng plugin sao lưu hoặc công cụ dòng lệnh để thực hiện điều này.

**Bước 2: Tạo sao lưu cơ sở dữ liệu**

Sử dụng phpMyAdmin hoặc dòng lệnh, sao lưu cơ sở dữ liệu WordPress. Sau đó, tải tệp sao lưu cơ sở dữ liệu lên máy tính của bạn.

**Bước 3: Di chuyển tệp tin WordPress**

Di chuyển tất cả các tệp tin của trang web WordPress từ máy chủ gốc sang máy chủ mới. Bạn có thể sử dụng FTP hoặc SCP để thực hiện điều này.

**Bước 4: Tạo cơ sở dữ liệu mới**

Trên máy chủ mới, tạo một cơ sở dữ liệu mới và người dùng cơ sở dữ liệu mới. Ghi nhớ thông tin đăng nhập của cơ sở dữ liệu này.

**Bước 5: Import cơ sở dữ liệu**

Sử dụng phpMyAdmin hoặc dòng lệnh, nhập cơ sở dữ liệu từ tệp sao lưu bạn đã tạo ở Bước 2 vào cơ sở dữ liệu mới trên máy chủ mới.

**Bước 6: Cập nhật tệp wp-config.php**

Trên máy chủ mới, mở tệp `wp-config.php` trong thư mục WordPress và cập nhật thông tin cơ sở dữ liệu (tên cơ sở dữ liệu, người dùng và mật khẩu) để phù hợp với cơ sở dữ liệu mới.

**Bước 7: Điều chỉnh các URL và đường dẫn**

Nếu địa chỉ URL của trang web mới khác với trang web gốc, bạn cần cập nhật URL bằng cách sử dụng một trong các cách sau:

- Sử dụng plugin như "Velvet Blues Update URLs" để tự động cập nhật các URL.
- Sử dụng công cụ dòng lệnh `wp-cli` để cập nhật URL: `wp search-replace '<http://old-url.com>' '<http://new-url.com>'`.

**Bước 8: Kiểm tra trang web**

Kiểm tra trang web trên máy chủ mới để đảm bảo rằng mọi thứ hoạt động đúng. Đặc biệt, kiểm tra trang web, cơ sở dữ liệu và các plugin. Bạn có thể gặp phải một số vấn đề do đường dẫn và URL đã thay đổi.

**Bước 9: Cấu hình DNS**

Cuối cùng, cấu hình tên miền hoặc DNS để trỏ đến máy chủ mới nếu bạn đang chuyển đổi máy chủ hoặc nhà cung cấp dịch vụ hosting.

Lưu ý rằng quá trình migrate WordPress có thể phức tạp và yêu cầu kiến thức về WordPress, cơ sở dữ liệu và máy chủ web. Hãy chắc chắn thực hiện sao lưu toàn bộ trang web và thực hiện thử nghiệm kỹ lưỡng trước khi thay đổi DNS để đảm bảo không mất dữ liệu quan trọng.