# Liệt kê các trang kiểm tra IP Public từ máy của KH khi hỗ trợ qua teamview hoặc yêu cầu KH cung cấp IP Public tại máy tính của KH để kiểm tra

Việc kiểm tra địa chỉ IP công cộng (public IP) trên máy tính của một khách hàng qua TeamViewer hoặc khi yêu cầu họ cung cấp thông tin này có thể thực hiện bằng các cách sau:

1. **Sử dụng TeamViewer**:
    - Nếu bạn đang sử dụng TeamViewer để hỗ trợ khách hàng từ xa, bạn có thể sử dụng tính năng của TeamViewer để xem thông tin về máy tính của họ. Sau khi kết nối với máy tính của khách hàng, bạn có thể thực hiện các bước sau:
    - Bấm vào tab "Extra" ở phía trên của cửa sổ TeamViewer.
    - Chọn "Remote System Information" để xem thông tin chi tiết về máy tính của khách hàng, bao gồm địa chỉ IP công cộng.
2. **Sử dụng trình duyệt web**:
    - Nếu không sử dụng TeamViewer hoặc khi yêu cầu khách hàng cung cấp thông tin IP, bạn có thể hướng dẫn họ sử dụng trình duyệt web để kiểm tra địa chỉ IP công cộng của máy tính của họ.
    - Đề nghị họ truy cập trang web kiểm tra IP như "[https://www.whatismyip.com](https://www.whatismyip.com/)" hoặc "[https://www.whatismyipaddress.com](https://www.whatismyipaddress.com/)". Trang web này sẽ hiển thị địa chỉ IP công cộng của họ ngay khi họ truy cập.
3. **Sử dụng lệnh trong Command Prompt (Windows) hoặc Terminal (Linux)**:
    - Nếu khách hàng đang sử dụng hệ điều hành Windows, bạn có thể hướng dẫn họ sử dụng Command Prompt và nhập lệnh sau:
        
        ```
        nslookup myip.opendns.com resolver1.opendns.com
        
        ```
        
    - Đối với hệ điều hành Linux, họ có thể sử dụng Terminal và thực hiện lệnh sau:
    hoặc
        
        ```
        curl ifconfig.me
        
        ```
        
        ```
        curl icanhazip.com
        
        ```
        
4. **Sử dụng trình quản lý mạng**:
    - Trong một số hệ điều hành, như Windows, người dùng có thể kiểm tra địa chỉ IP công cộng bằng cách mở "Network and Sharing Center" (Trung tâm Mạng và Chia sẻ) và chọn "View your active networks." Địa chỉ IP công cộng sẽ hiển thị dưới mục "Connections."

Hãy đảm bảo rằng bạn cung cấp hướng dẫn cụ thể cho khách hàng về cách kiểm tra địa chỉ IP công cộng dựa trên hệ điều hành của họ.