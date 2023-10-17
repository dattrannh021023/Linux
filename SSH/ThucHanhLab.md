# 1. Xác thực bằng mật khẩu
Cấu hình SSH Server để quản lý máy chủ từ xa
- OpenSSH đã được cài đặt mặc định khi ta đã cài đặt CentOS Stream với Cài đặt [Tối thiểu], do đó không cần cài đặt các gói mới.
- Ta có thể đăng nhập bằng Xác thực mật khẩu theo mặc định.
Nếu muốn cải thiện tính bảo mật, ta nên thay đổi tham số PermitRootLogin.

```
[root@dlp ~]#vi /etc/ssh/sshd_config
# dòng 40: thay đổi ( cấm đăng nhập root )
# đối với các tùy chọn khác thì có [prohibit-password], [forced-commands-only]
Giấy phépRootĐăng nhậpKHÔNG
[root@dlp ~]#systemctl khởi động lại sshd
```