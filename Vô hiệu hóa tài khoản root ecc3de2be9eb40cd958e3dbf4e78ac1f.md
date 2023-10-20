# Vô hiệu hóa tài khoản root

Vô hiệu hóa tài khoản root trên một máy chủ Linux là một biện pháp bảo mật quan trọng, vì tài khoản root có quyền truy cập và thực thi tất cả các tác vụ trên hệ thống. Thay vì sử dụng tài khoản root, bạn nên tạo một tài khoản người dùng khác với quyền sudo (superuser) để thực hiện các tác vụ quản trị. Dưới đây là hướng dẫn cách vô hiệu hóa tài khoản root trên Linux:

**Bước 1: Đăng nhập vào máy chủ với quyền sudo**
Đảm bảo bạn đang đăng nhập vào máy chủ với một tài khoản có quyền sudo. Nếu bạn không có quyền sudo, bạn cần truy cập với một tài khoản có quyền quản trị khác và sau đó thực hiện các bước sau để vô hiệu hóa tài khoản root.

**Bước 2: Đảm bảo bạn có một tài khoản sudo**
Trước khi vô hiệu hóa tài khoản root, đảm bảo bạn đã cấu hình một tài khoản người dùng khác có quyền sudo (superuser) để thực hiện các tác vụ quản trị hệ thống. Nếu bạn chưa có tài khoản như vậy, hãy tạo một tài khoản và cấu hình quyền sudo cho nó.

**Bước 3: Thực hiện vô hiệu hóa tài khoản root**
Để vô hiệu hóa tài khoản root, bạn có thể sử dụng lệnh `passwd` để đặt mật khẩu không thể dự đoán hoặc sử dụng lệnh `usermod` để khóa tài khoản root.

- **Sử dụng `passwd`**:
    
    ```bash
    sudo passwd -l root
    
    ```
    
- **Sử dụng `usermod`**:
    
    ```bash
    sudo usermod -p '!' root
    
    ```
    

Sử dụng một trong hai lệnh trên sẽ làm cho tài khoản root không thể đăng nhập bằng mật khẩu. Tài khoản vẫn tồn tại, nhưng sẽ không thể sử dụng mật khẩu để đăng nhập. Thay vào đó, bạn nên sử dụng tài khoản người dùng có quyền sudo để thực hiện các tác vụ quản trị.

Lưu ý rằng nếu bạn cần kích hoạt lại tài khoản root trong tương lai, bạn có thể sử dụng lệnh tương tự để mở khóa tài khoản.