# Cấu hình nginx làm proxy cho web server (web server sử dụng Apache)

Để cấu hình Nginx làm proxy cho một máy chủ web sử dụng Apache, bạn cần thực hiện các bước sau:

1. **Cài đặt Nginx**: Đảm bảo rằng bạn đã cài đặt Nginx trên máy chủ của mình. Sử dụng trình quản lý gói của hệ điều hành (ví dụ: `apt`, `yum`, `dnf`) để cài đặt Nginx.
2. **Tạo tệp cấu hình Nginx**: Tạo một tệp cấu hình Nginx cho trang web bạn muốn chuyển hướng. Ví dụ, bạn có thể tạo một tệp với tên `mywebsite.conf` trong thư mục cấu hình Nginx (thường nằm trong `/etc/nginx/conf.d/`).
3. **Cấu hình Nginx Proxy**: Sửa tệp cấu hình Nginx bạn vừa tạo bằng việc thêm cấu hình proxy. Dưới đây là một ví dụ cơ bản:

```
server {
    listen 80;
    server_name mywebsite.com; # Thay thế bằng tên miền của bạn

    location / {
        proxy_pass <http://127.0.0.1:8080>; # Thay đổi cổng này nếu cần
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}

```

- Trong ví dụ trên, `server_name` là tên miền của trang web mà bạn muốn chuyển hướng.
- Dòng `proxy_pass` xác định máy chủ và cổng của máy chủ Apache. Trong trường hợp này, Apache đang chạy trên cùng máy chủ với Nginx và cổng là 8080. Điều này có thể thay đổi tùy theo cài đặt của bạn.
1. **Kiểm tra cấu hình Nginx**: Trước khi áp dụng cấu hình, hãy kiểm tra xem tệp cấu hình có lỗi cú pháp hay không:

```bash
sudo nginx -t

```

Nếu không có lỗi cú pháp, bạn sẽ thấy thông báo "syntax is okay" và "test is successful."

1. **Khởi động lại Nginx**: Sau khi cấu hình đã được kiểm tra và không có lỗi, hãy khởi động lại dịch vụ Nginx để áp dụng cấu hình:

```bash
sudo systemctl restart nginx

```

Bây giờ, Nginx sẽ chuyển hướng yêu cầu đến máy chủ Apache và chấp nhận yêu cầu từ trình duyệt.

Chắc chắn rằng bạn đã cài đặt và cấu hình máy chủ Apache để lắng nghe trên cổng được xác định trong tệp cấu hình Nginx.

Lưu ý rằng nếu máy chủ Apache và Nginx nằm trên hai máy chủ khác nhau, bạn cần xác định địa chỉ IP hoặc tên miền của máy chủ Apache trong cấu hình proxy của Nginx.