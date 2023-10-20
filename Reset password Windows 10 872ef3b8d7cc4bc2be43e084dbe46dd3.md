# Reset password Windows 10

Để reset mật khẩu của tài khoản root (tài khoản Administrator) trên Windows 10, bạn cần có quyền quản trị hoặc quyền truy cập vào tài khoản Administrator khác. Dưới đây là một số cách để bạn reset mật khẩu tài khoản Administrator trên Windows 10:

**Lưu ý quan trọng**: Việc reset mật khẩu tài khoản Administrator nên được thực hiện cẩn thận và chỉ khi bạn có quyền truy cập vào hệ thống hoặc được ủy quyền.

1. **Sử dụng Tài khoản Administrator khác (nếu có)**:
    
    Nếu bạn đã đăng nhập vào một tài khoản Administrator khác, bạn có thể sử dụng tài khoản đó để reset mật khẩu Administrator:
    
    - Bước 1: Đăng nhập vào tài khoản Administrator khác.
    - Bước 2: Mở Command Prompt (Cmd) với quyền quản trị bằng cách tìm kiếm "cmd" trong menu Start, nhấn chuột phải lên "Command Prompt" và chọn "Run as administrator".
    - Bước 3: Sử dụng lệnh `net user` để đặt lại mật khẩu cho tài khoản Administrator. Ví dụ:
        
        ```
        net user Administrator new_password
        
        ```
        
        Thay `new_password` bằng mật khẩu mới.
        
2. **Sử dụng Ổ đĩa cài đặt hoặc USB Boot**:
    
    Bạn có thể sử dụng ổ đĩa cài đặt hoặc USB Boot của Windows để thực hiện việc reset mật khẩu. Dưới đây là các bước cơ bản:
    
    - Bước 1: Boot từ ổ đĩa cài đặt hoặc USB Boot.
    - Bước 2: Chọn ngôn ngữ và chọn "Repair your computer".
    - Bước 3: Chọn "Troubleshoot" > "Advanced options" > "Command Prompt".
    - Bước 4: Sử dụng lệnh `net user` để đặt lại mật khẩu cho tài khoản Administrator:
        
        ```
        net user Administrator new_password
        
        ```
        
        Thay `new_password` bằng mật khẩu mới.
        
3. **Sử dụng phần mềm bên ngoài**:
    
    Có nhiều phần mềm bên ngoài mà bạn có thể sử dụng để reset mật khẩu tài khoản Administrator trên Windows 10. Một số ví dụ phổ biến bao gồm Ophcrack, Offline NT Password & Registry Editor, và PCUnlocker. Hãy thực hiện nghiên cứu và chọn một phần mềm phù hợp với bạn.