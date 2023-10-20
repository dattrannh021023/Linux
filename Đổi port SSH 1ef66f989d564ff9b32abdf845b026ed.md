# Đổi port SSH

Để đổi port SSH mặc định (port 22) trên một máy chủ Linux, bạn cần tuân thủ các bước sau:

1. **Đăng nhập vào máy chủ**:
Sử dụng kết nối SSH hiện tại hoặc truy cập trực tiếp vào máy chủ nếu bạn có quyền truy cập vật lý hoặc quyền truy cập qua máy chủ ảo.
2. **Sửa tệp cấu hình SSH**:
Tệp cấu hình SSH là `/etc/ssh/sshd_config`. Bạn cần sửa tệp này bằng một trình soạn thảo văn bản như `nano`, `vim`, hoặc `gedit`. Dùng lệnh sau để mở tệp cấu hình SSH:
    
    ```bash
    sudo nano /etc/ssh/sshd_config
    
    ```
    
3. **Tìm và sửa đổi cổng SSH**:
Tìm dòng chứa `Port 22` (port mặc định) và thay đổi số 22 thành số cổng bạn muốn sử dụng, ví dụ 2222:
    
    ```
    Port 2222
    
    ```
    
4. **Lưu và thoát**:
Trong `nano`, bạn có thể lưu tệp bằng cách nhấn `Ctrl + O`, sau đó nhấn Enter để xác nhận. Để thoát, nhấn `Ctrl + X`.
5. **Khởi động lại dịch vụ SSH**:
Sau khi bạn đã thay đổi cổng SSH, bạn cần khởi động lại dịch vụ SSH để áp dụng thay đổi:
    
    ```bash
    sudo service ssh restart
    
    ```
    
    hoặc
    
    ```bash
    sudo systemctl restart ssh
    
    ```
    
6. **Kiểm tra kết nối mới**:
Sau khi bạn đã thay đổi cổng SSH, bạn cần kết nối lại vào máy chủ bằng SSH, nhưng lần này sử dụng cổng mới. Ví dụ:
    
    ```bash
    ssh username@your_server_ip -p 2222
    
    ```
    
    Trong đó, `username` là tên người dùng của bạn và `your_server_ip` là địa chỉ IP của máy chủ.
    

Chắc chắn rằng bạn ghi nhớ cổng SSH mới và chỉ sử dụng nó để kết nối vào máy chủ. Thay đổi cổng SSH có thể tăng bảo mật bằng cách làm cho máy chủ tránh bị quét và tấn công mạng.