# Bật slow query log của MYSQL, MariaDB

Để bật slow query log trong MySQL hoặc MariaDB, bạn cần thực hiện các bước sau:

1. Mở tệp cấu hình MySQL hoặc MariaDB (`my.cnf` hoặc `my.ini`), tùy thuộc vào hệ điều hành bạn đang sử dụng. Thường thì tệp cấu hình này được đặt ở `/etc/mysql/my.cnf` hoặc `/etc/my.cnf` trên Linux hoặc `C:\\ProgramData\\MySQL\\MySQL Server X.Y\\my.ini` trên Windows.
2. Tìm và chỉnh sửa phần cấu hình của slow query log. Bạn có thể thêm các tùy chọn sau vào tệp cấu hình:
    
    ```
    slow_query_log = 1
    slow_query_log_file = /var/log/mysql/mysql-slow.log
    long_query_time = 1
    log_queries_not_using_indexes = 1
    
    ```
    
    - `slow_query_log`: Đặt thành 1 để bật slow query log.
    - `slow_query_log_file`: Đặt đường dẫn đến tệp log nơi các truy vấn chậm sẽ được ghi.
    - `long_query_time`: Đây là ngưỡng thời gian, tính bằng giây. Bất kỳ truy vấn nào mà thời gian thực thi vượt quá giới hạn này sẽ được ghi vào tệp log. Trong ví dụ trên, tất cả truy vấn chậm hơn 1 giây sẽ được ghi vào tệp log.
    - `log_queries_not_using_indexes`: Đặt thành 1 để ghi cảnh báo về các truy vấn không sử dụng index.
3. Lưu tệp cấu hình sau khi thay đổi.
4. Khởi động lại MySQL hoặc MariaDB để áp dụng các thay đổi:
    
    ```
    sudo service mysql restart
    
    ```
    
    Hoặc:
    
    ```
    sudo systemctl restart mysql
    
    ```
    

Sau khi thực hiện các bước trên, slow query log sẽ được kích hoạt và các truy vấn chậm sẽ được ghi vào tệp log được chỉ định. Bạn có thể theo dõi tệp log để kiểm tra các truy vấn chậm và tối ưu hóa hệ thống cơ sở dữ liệu của mình.