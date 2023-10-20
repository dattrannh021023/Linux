# Kiểm tra trạng thái Port (Mở hoặc đóng), kiểm tra Port đang được sử dụng bởi dịch vụ nào

Để kiểm tra trạng thái mở hoặc đóng của một cổng (port) và xem cổng đó đang được sử dụng bởi dịch vụ nào, bạn có thể sử dụng một số lệnh và công cụ trên hệ thống Linux.

Dưới đây là một số cách để thực hiện kiểm tra này:

### 1. Sử dụng lệnh `netstat`:

Lệnh `netstat` cho phép bạn kiểm tra trạng thái của các cổng trên hệ thống và xem dịch vụ nào đang sử dụng chúng. Để kiểm tra một cổng cụ thể (ví dụ, cổng 80), sử dụng lệnh sau:

```bash
netstat -tuln | grep 80

```

Trong đó:

- `t` (hoặc `-tcp`) chỉ hiển thị cổng TCP.
- `u` (hoặc `-udp`) chỉ hiển thị cổng UDP.
- `l` (hoặc `-listening`) chỉ hiển thị cổng đang lắng nghe.
- `n` (hoặc `-numeric`) hiển thị địa chỉ IP và cổng dưới dạng số thay vì ánh xạ tên miền.

Lệnh này sẽ liệt kê tất cả các kết nối hoặc dịch vụ đang sử dụng cổng 80 (hoặc cổng bạn muốn kiểm tra).

### 2. Sử dụng lệnh `ss`:

Lệnh `ss` là một công cụ tương tự như `netstat` để kiểm tra trạng thái mở hoặc đóng của cổng và xem dịch vụ đang sử dụng chúng. Ví dụ:

```bash
ss -tuln | grep 80

```

### 3. Sử dụng `lsof` (List Open Files):

Lệnh `lsof` cho phép bạn liệt kê tất cả các tệp và cổng đang được mở bởi các quy trình trên hệ thống. Để kiểm tra cổng 80, sử dụng lệnh sau:

```bash
sudo lsof -i :80

```

Lệnh này sẽ hiển thị danh sách các quy trình và dịch vụ đang sử dụng cổng 80.

### 4. Sử dụng `nmap`:

Nếu bạn cần kiểm tra các cổng trên một máy chủ từ một máy tính khác, bạn có thể sử dụng `nmap`. Ví dụ:

```bash
nmap -p 80 your_server_ip

```

Thay `your_server_ip` bằng địa chỉ IP của máy chủ bạn muốn kiểm tra.

Lưu ý rằng để chạy một số lệnh này, bạn có thể cần quyền sudo hoặc phải đăng nhập với quyền quản trị trên hệ thống.