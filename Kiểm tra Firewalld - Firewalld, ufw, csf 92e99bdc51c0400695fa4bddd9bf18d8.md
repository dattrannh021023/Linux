# Kiểm tra Firewalld: - Firewalld, ufw, csf

Firewalld, UFW (Uncomplicated Firewall), và CSF (ConfigServer Security & Firewall) là các công cụ quản lý tường lửa trên hệ thống Linux. Dưới đây là cách kiểm tra trạng thái của mỗi công cụ:

1. **Firewalld**:
    - Để kiểm tra trạng thái Firewalld, bạn có thể chạy lệnh sau trong dòng lệnh:
        
        ```bash
        sudo systemctl status firewalld
        
        ```
        
    - Để kiểm tra tất cả các luật đã được cấu hình trong Firewalld, bạn có thể sử dụng lệnh sau:
        
        ```
        sudo firewall-cmd --list-all
        
        ```
        
2. **UFW (Uncomplicated Firewall)**:
    - Để kiểm tra trạng thái UFW, bạn có thể chạy lệnh sau:
        
        ```
        sudo ufw status
        
        ```
        
    - Để kiểm tra tất cả các luật đã được cấu hình trong UFW, bạn có thể sử dụng lệnh:
        
        ```
        sudo ufw status verbose
        
        ```
        
3. **CSF (ConfigServer Security & Firewall)**:
    - Để kiểm tra trạng thái CSF, bạn có thể chạy lệnh sau:
        
        ```
        sudo csf -s
        
        ```
        
    - Để xem danh sách các luật được áp dụng trong CSF, bạn có thể kiểm tra tập tin cấu hình `/etc/csf/csf.conf` hoặc sử dụng các lệnh cụ thể của CSF như `csf -l` để liệt kê các IP bị chặn.

Chú ý rằng để thực hiện các lệnh trên, bạn cần có quyền quản trị hoặc sử dụng `sudo`. Điều này đảm bảo bạn có quyền truy cập để kiểm tra và quản lý tường lửa trên hệ thống Linux của bạn.