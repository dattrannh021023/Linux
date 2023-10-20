# Cấu hình redirect web site từ non-www sang www

Để cấu hình chuyển hướng (redirect) một trang web từ phiên bản không "www" (ví dụ: [example.com](http://example.com/)) sang phiên bản "www" (ví dụ: [www.example.com](http://www.example.com/)) trên máy chủ web, bạn có thể sử dụng các tùy chọn sau đây dựa trên loại máy chủ web mà bạn đang sử dụng. Hãy chắc chắn rằng bạn có quyền truy cập vào cấu hình máy chủ web trước khi thực hiện thay đổi.

### Cấu hình Chuyển hướng trong Apache

Đối với máy chủ web sử dụng Apache, bạn có thể sử dụng tệp `.htaccess` để cấu hình chuyển hướng. Đảm bảo module `mod_rewrite` đã được bật. Sửa hoặc tạo một tệp `.htaccess` trong thư mục gốc của trang web và thêm mã sau:

```
RewriteEngine on
RewriteCond %{HTTP_HOST} !^www\\. [NC]
RewriteRule ^(.*)$ <http://www>.%{HTTP_HOST}/$1 [R=301,L]

```

Lưu ý rằng điều này sẽ tạo một chuyển hướng 301, nghĩa là một chuyển hướng vĩnh viễn, và trình duyệt của người dùng sẽ tự động cập nhật URL.

### Cấu hình Chuyển hướng trong Nginx

Đối với máy chủ web sử dụng Nginx, bạn có thể chỉnh sửa cấu hình trang web trong tệp cấu hình Nginx. Tìm tệp cấu hình của trang web (thường nằm trong thư mục `/etc/nginx/conf.d/` hoặc `/etc/nginx/sites-available/`) và thêm dòng sau trong khối server:

```
server {
    listen 80;
    server_name example.com;
    return 301 $scheme://www.example.com$request_uri;
}

```

Sau khi bạn đã thực hiện thay đổi này, hãy khởi động lại dịch vụ Nginx để áp dụng chuyển hướng:

```bash
sudo systemctl restart nginx

```

### Cấu hình Chuyển hướng trong cPanel

Nếu bạn sử dụng cPanel để quản lý máy chủ web của mình, bạn có thể thực hiện chuyển hướng từ phiên bản không "www" sang "www" bằng cách thực hiện các bước sau:

1. Đăng nhập vào cPanel của bạn.
2. Tìm và mở mục "Domains" hoặc "Domains" trong cPanel.
3. Chọn tùy chọn "Redirects" hoặc "Redirects" trong danh sách các công cụ.
4. Trong trang "Redirects," bạn sẽ thấy mục "Add Redirect." Chọn mục này.
5. Trong mục "Type," chọn "Permanent (301)."
6. Trong mục "https?://(www\.)?" của "http://," nhập tên miền chính của bạn (ví dụ: [example.com](http://example.com/)).
7. Trong mục "Redirects to," nhập địa chỉ URL mới với "www" (ví dụ: [http://www.example.com](http://www.example.com/)).
8. Chọn tùy chọn "Wild Card Redirect" nếu bạn muốn áp dụng chuyển hướng cho mọi đường dẫn dưới "[example.com](http://example.com/)."
9. Bấm vào nút "Add."

Chuyển hướng sẽ được cấu hình và áp dụng ngay lập tức.

Hãy chắc chắn kiểm tra lại trang web để đảm bảo chuyển hướng đã hoạt động như mong đợi.