# Tìm hiểu về giao thức DHCP, sử dụng TCPDUMP để bắt gói tin và chứng minh lý thuyết của giao thức DHCP

Giao thức DHCP (Dynamic Host Configuration Protocol) là một giao thức mạng dùng để cấu hình động các thiết bị mạng, như máy tính, điện thoại IP, máy chủ, và nhiều thiết bị khác, giúp chúng lấy được địa chỉ IP, máscara mạng, cổng gateway, máy chủ DNS và các thiết lập mạng khác một cách tự động. Giao thức này giúp đơn giản hóa việc quản lý và cấu hình mạng, đặc biệt trong các mạng lớn và phức tạp.

Một phiên làm việc DHCP thông thường bao gồm các bước sau:

1. DHCP Discover: Thiết bị yêu cầu cấu hình mạng bằng cách gửi một gói tin "DHCP Discover" qua mạng. Gói tin này chứa thông tin như địa chỉ MAC của thiết bị và yêu cầu cấu hình.
2. DHCP Offer: Sau khi nhận được gói tin "DHCP Discover," máy chủ DHCP cung cấp một đề nghị cấu hình bằng cách gửi một gói tin "DHCP Offer" chứa thông tin cấu hình đề xuất.
3. DHCP Request: Thiết bị DHCP chấp nhận đề nghị cấu hình bằng cách gửi một gói tin "DHCP Request" yêu cầu cấu hình với máy chủ DHCP.
4. DHCP Acknowledgment: Máy chủ DHCP xác nhận yêu cầu bằng cách gửi một gói tin "DHCP Acknowledgment" với thông tin cấu hình cuối cùng. Thiết bị nhận được gói tin này và áp dụng cấu hình.

Để chứng minh lý thuyết của giao thức DHCP và bắt gói tin sử dụng `tcpdump`, bạn cần truy cập vào một máy tính chạy hệ điều hành Linux hoặc Unix (bao gồm cả macOS) với quyền truy cập root hoặc quyền sudo. Sau đây là một ví dụ về cách sử dụng `tcpdump` để bắt gói tin DHCP:

1. Mở terminal trên máy tính Linux hoặc Unix.
2. Chạy lệnh sau để bắt gói tin DHCP:

```bash
sudo tcpdump -i <interface> -n port 67 or port 68

```

Trong đó:

- `<interface>` là tên của giao diện mạng bạn muốn theo dõi, ví dụ: `eth0` hoặc `wlan0`.

Lệnh này sẽ bắt và hiển thị các gói tin DHCP trên giao diện được chỉ định.

1. Bây giờ, kích hoạt một thiết bị trên cùng mạng với máy tính của bạn (ví dụ: kết nối một điện thoại hoặc máy tính khác vào mạng WiFi) hoặc thực hiện một yêu cầu DHCP khác trên mạng.
2. Bạn sẽ thấy các gói tin DHCP xuất hiện trong kết quả của `tcpdump`. Các gói tin DHCP Discover, Offer, Request và Acknowledgment sẽ xuất hiện trong danh sách.