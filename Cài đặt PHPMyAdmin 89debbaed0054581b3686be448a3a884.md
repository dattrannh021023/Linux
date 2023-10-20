# Cài đặt PHPMyAdmin

PHPMyAdmin là một công cụ quản lý cơ sở dữ liệu MySQL thông qua giao diện web. Đây là hướng dẫn cài đặt PHPMyAdmin trên một máy chủ Linux sử dụng Apache, MySQL (hoặc MariaDB), và PHP. Dưới đây, tôi sẽ hướng dẫn cài đặt PHPMyAdmin trên một hệ thống Linux dựa trên hệ điều hành Ubuntu hoặc Debian.

**Bước 1: Cài đặt PHPMyAdmin và gói phụ thuộc**

1. Mở terminal trên máy chủ Linux của bạn.
2. Cài đặt PHPMyAdmin và các gói phụ thuộc cần thiết bằng lệnh sau:
    
    ```bash
    sudo apt update
    sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
    
    ```
    
    Trong quá trình cài đặt, bạn sẽ được yêu cầu chọn máy chủ web mà bạn đang sử dụng (thường là Apache2) và sau đó xác nhận.
    
3. Trong quá trình cài đặt, bạn sẽ được yêu cầu cấu hình PHPMyAdmin. Chọn "apache2" bằng cách sử dụng mũi tên lên/xuống và nhấn Enter. Sau đó, bạn sẽ được hỏi nếu bạn muốn cho phép cấu hình "dbconfig-common" cho PHPMyAdmin. Chọn "Yes" và sau đó cung cấp mật khẩu gốc của MySQL hoặc MariaDB khi được yêu cầu.

**Bước 2: Cấu hình PHPMyAdmin để làm việc với MySQL/MariaDB**

1. Để kết nối PHPMyAdmin với cơ sở dữ liệu MySQL hoặc MariaDB, bạn cần cấu hình kết nối. Mở terminal và chạy lệnh sau:
    
    ```bash
    sudo phpenmod mbstring
    sudo systemctl restart apache2
    
    ```
    
2. Truy cập vào file cấu hình của PHPMyAdmin:
    
    ```bash
    sudo nano /etc/phpmyadmin/config.inc.php
    
    ```
    
3. Tìm và thêm dòng sau vào file cấu hình:
    
    ```php
    $cfg['Servers'][$i]['auth_type'] = 'cookie';
    
    ```
    
    Lưu tệp và thoát.
    

**Bước 3: Khởi động lại Apache**

1. Khởi động lại Apache để áp dụng các thay đổi:
    
    ```bash
    sudo systemctl restart apache2
    
    ```
    

**Bước 4: Truy cập PHPMyAdmin qua trình duyệt**

Truy cập PHPMyAdmin bằng cách điền địa chỉ IP hoặc tên miền máy chủ của bạn, sau đó thêm `/phpmyadmin` vào URL. Ví dụ: `http://your_server_ip/phpmyadmin`.

Sử dụng tên người dùng và mật khẩu của người quản trị cơ sở dữ liệu MySQL/MariaDB để đăng nhập vào PHPMyAdmin.

Đó là cách cài đặt PHPMyAdmin trên một máy chủ Linux dựa trên hệ điều hành Ubuntu hoặc Debian. Nếu bạn sử dụng hệ thống khác, các bước có thể có sự khác biệt nhỏ.