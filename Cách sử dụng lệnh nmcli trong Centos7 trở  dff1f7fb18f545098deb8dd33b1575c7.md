# Cách sử dụng lệnh nmcli trong Centos7 trở lên để đặt IP (yêu cầu cần gắn từ 2 card mạng trở lên cho máy LAB)

Lệnh `nmcli` là một công cụ dòng lệnh mạng cho NetworkManager, một trình quản lý mạng được sử dụng trong hệ điều hành CentOS 7 trở lên. Để đặt IP cho các card mạng trên CentOS 7 trở lên bằng `nmcli`, bạn có thể thực hiện các bước sau:

1. **Kiểm tra danh sách card mạng hiện có**:
    
    ```
    nmcli device status
    
    ```
    
    Lệnh này sẽ liệt kê danh sách các card mạng hiện có trên máy của bạn.
    
2. **Xác định tên giao diện mạng** (Network Interface Name) cho từng card mạng mà bạn muốn cấu hình.
3. **Đặt IP cho card mạng**:
    
    ```
    nmcli connection modify "tên_kết_nối" ipv4.address IP/mask ipv4.gateway Gateway
    
    ```
    
    Thay thế các giá trị sau:
    
    - `"tên_kết_nối"`: Tên của kết nối bạn muốn cấu hình (ví dụ: `Wired connection 1`).
    - `IP/mask`: Địa chỉ IP và mạng con (ví dụ: `192.168.1.10/24`).
    - `Gateway`: Địa chỉ IP của cổng mặc định.
    
    Ví dụ:
    
    ```
    nmcli connection modify "Wired connection 1" ipv4.address 192.168.1.10/24 ipv4.gateway 192.168.1.1
    
    ```
    
4. **Khởi động lại kết nối mạng**:
    
    ```
    nmcli connection up "tên_kết_nối"
    
    ```
    
    Ví dụ:
    
    ```
    nmcli connection up "Wired connection 1"
    
    ```
    

Lưu ý rằng bạn có thể thay đổi tên kết nối, địa chỉ IP, mạng con và cổng mặc định theo nhu cầu của bạn. Hãy chắc chắn rằng tên kết nối được chọn đã tồn tại trong danh sách kết nối mạng trước khi bạn thực hiện cấu hình. Sau khi thực hiện các bước trên, máy của bạn sẽ có IP cấu hình cho card mạng được chỉ định.