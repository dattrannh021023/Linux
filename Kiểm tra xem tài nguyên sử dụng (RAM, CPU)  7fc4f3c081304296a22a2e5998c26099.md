# Kiểm tra xem tài nguyên sử dụng (RAM, CPU) đối với MySQL, HTTP bằng lệnh.

Để kiểm tra tài nguyên sử dụng (RAM, CPU) cho các dịch vụ như MySQL và HTTP, bạn có thể sử dụng một số lệnh hệ thống. Dưới đây là cách bạn có thể kiểm tra chúng:

1. **Kiểm tra tài nguyên cho MySQL:**
    
    Để xem tài nguyên sử dụng bởi MySQL, bạn có thể sử dụng lệnh `top` hoặc `htop`. Đảm bảo rằng MySQL đang chạy trước khi sử dụng lệnh này. Chạy lệnh sau đây:
    
    ```bash
    top
    
    ```
    
    Sau đó, bạn có thể nhấn `Shift + M` để sắp xếp theo tài nguyên RAM sử dụng hoặc `Shift + P` để sắp xếp theo tài nguyên CPU sử dụng.
    
    Nếu bạn muốn kiểm tra tài nguyên cho MySQL cụ thể, bạn có thể sử dụng lệnh `mysqladmin`:
    
    ```bash
    mysqladmin processlist
    
    ```
    
2. **Kiểm tra tài nguyên cho HTTP (ví dụ: Apache hoặc Nginx):**
    
    Để kiểm tra tài nguyên sử dụng bởi máy chủ HTTP như Apache hoặc Nginx, bạn cũng có thể sử dụng `top` hoặc `htop`. Nếu bạn đang sử dụng Apache, thử lệnh sau:
    
    ```bash
    top
    
    ```
    
    Tìm quá trình Apache và xem tài nguyên RAM và CPU sử dụng.
    
    Nếu bạn đang sử dụng Nginx, sử dụng lệnh sau:
    
    ```bash
    top
    
    ```
    
    Tìm quá trình Nginx và xem tài nguyên RAM và CPU sử dụng.
    

Nhớ rằng việc kiểm tra tài nguyên này có thể đòi hỏi quyền quản trị hệ thống. Ngoài ra, để biết chi tiết hơn về cách quản lý tài nguyên hệ thống và theo dõi các dịch vụ cụ thể, bạn nên xem xét sử dụng các công cụ quản lý tài nguyên hệ thống như `top`, `htop`, `iotop`, và các công cụ quản lý MySQL hoặc HTTP cụ thể nếu có.