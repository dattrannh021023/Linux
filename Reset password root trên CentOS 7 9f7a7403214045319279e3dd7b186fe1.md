# Reset password root trên CentOS 7

Để reset mật khẩu của tài khoản root trên CentOS 7, ta cần truy cập vào chế độ single user (còn được gọi là chế độ dòng lệnh đơn) hoặc sử dụng một live CD/USB để thay đổi mật khẩu. Dưới đây là cách ta có thể thực hiện việc này trong chế độ single user:

**Lưu ý quan trọng**: Đảm bảo ta có quyền quản trị để thực hiện các thay đổi này. Việc reset mật khẩu root nên được thực hiện cẩn thận và chỉ khi ta đã quên mật khẩu gốc.

1. Khởi động lại máy tính CentOS 7 của ta. Khi máy tính đang khởi động, ta cần nhấn một phím (ví dụ: Esc, Shift, hoặc Space) để hiển thị màn hình Grub (boot menu). Sau đó, chọn CentOS 7 và nhấn phím "e" để chỉnh sửa các tùy chọn khởi động.
2. Tìm dòng chứa `ro` (read-only) và sửa thành `rw` (read-write).
3. Thêm dòng `init=/bin/bash` vào cuối dòng vừa chỉnh sửa. Dòng lệnh sau khi chỉnh sửa có thể giống như sau:
    
    ```
    linux16 /vmlinuz-3.10.0-1160.11.1.el7.x86_64 root=UUID=your-root-UUID ro crashkernel=auto rd.lvm.lv=your-root-lv rd.lvm.lv=your-swap-lv rd.lvm.lv=your-home-lv rhgb quiet LANG=en_US.UTF-8 init=/bin/bash
    
    ```
    
    Lưu ý thay thế `your-root-UUID`, `your-root-lv`, `your-swap-lv`, và `your-home-lv` bằng thông tin thực tế của hệ thống của bạn.
    
4. Nhấn `Ctrl + X` hoặc `Ctrl + B` để khởi động lại CentOS 7 trong chế độ dòng lệnh đơn (single user).
5. Ta sẽ thấy một dòng lệnh dòng lệnh `bash`. Sử dụng lệnh `passwd` để đặt mật khẩu mới cho tài khoản root:
    
    ```
    passwd
    
    ```
    
6. Nhập mật khẩu mới cho tài khoản root và xác nhận nó.
7. Sau khi ta đã đặt lại mật khẩu, sử dụng lệnh `sync` để đồng bộ hóa dữ liệu và sau đó khởi động lại hệ thống bằng lệnh:
    
    ```
    reboot -f
    
    ```
    
8. Máy tính sẽ khởi động lại và ta có thể đăng nhập vào tài khoản root bằng mật khẩu mới.