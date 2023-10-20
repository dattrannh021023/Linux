# Cài đặt và đồng bộ hóa thời gian qua NTP (Network Time Protocol)

1. **Cài đặt NTP Client**:
    
    Đầu tiên, bạn cần cài đặt gói phần mềm NTP client. Trong hầu hết các bản phân phối Linux, bạn có thể sử dụng các lệnh sau để cài đặt NTP:
    
    Trên Ubuntu hoặc Debian:
    
    ```bash
    sudo apt-get update
    sudo apt-get install ntp
    
    ```
    
    Trên CentOS hoặc Fedora:
    
    ```bash
    sudo yum install ntp
    
    ```
    
2. **Cấu hình NTP Client**:
    
    Mở tệp cấu hình của NTP client, thường là `/etc/ntp.conf`, bằng trình soạn thảo văn bản như `nano` hoặc `vi`:
    
    ```bash
    sudo nano /etc/ntp.conf
    
    ```
    
    Trong tệp này, bạn có thể chỉnh sửa các máy chủ NTP mà bạn muốn sử dụng để đồng bộ hóa thời gian. Thêm hoặc chỉnh sửa dòng sau để thêm máy chủ NTP:
    
    ```
    server pool.ntp.org
    
    ```
    
    Hoặc nếu bạn biết các máy chủ NTP cụ thể, thay vì `pool.ntp.org`, bạn có thể thay thế bằng địa chỉ IP của máy chủ NTP. Sau khi sửa đổi, lưu lại và đóng tệp cấu hình.
    
3. **Khởi động và Kích hoạt dịch vụ NTP**:
    
    Bạn cần khởi động và kích hoạt dịch vụ NTP để NTP client bắt đầu đồng bộ hóa thời gian:
    
    Trên Ubuntu hoặc Debian:
    
    ```bash
    sudo service ntp start
    sudo service ntp status
    
    ```
    
    Trên CentOS hoặc Fedora:
    
    ```bash
    sudo systemctl start ntpd
    sudo systemctl enable ntpd
    
    ```
    
4. **Kiểm tra Đồng bộ hóa NTP**:
    
    Để kiểm tra xem NTP client đã đồng bộ hóa thời gian thành công hay chưa, bạn có thể sử dụng lệnh `ntpq` hoặc `ntpdate`:
    
    ```
    ntpq -p
    
    ```
    
    hoặc
    
    ```
    ntpdate -q pool.ntp.org
    
    ```
    
    Nếu bạn nhận được thông điệp "reach = 377", nghĩa là NTP client đã kết nối thành công và đã đồng bộ hóa thời gian.
    
5. **Tự động đồng bộ hóa thời gian**:
    
    Để đảm bảo rằng thời gian được đồng bộ hóa tự động khi máy tính khởi động, bạn nên kích hoạt dịch vụ NTP để khởi chạy cùng hệ thống:
    
    Trên Ubuntu hoặc Debian:
    
    ```bash
    sudo update-rc.d ntp enable
    
    ```
    
    Trên CentOS hoặc Fedora:
    
    ```bash
    sudo systemctl enable ntpd
    
    ```
    

Như vậy, bạn đã cài đặt và đồng bộ hóa thời gian qua NTP trên hệ điều hành Linux của mình. Thời gian của máy tính sẽ được duy trì và đồng bộ hóa với máy chủ NTP bạn đã cấu hình.