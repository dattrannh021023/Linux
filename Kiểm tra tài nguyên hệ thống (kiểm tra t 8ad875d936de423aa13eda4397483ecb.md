# Kiểm tra tài nguyên hệ thống (kiểm tra tiến trình sử dụng nhiều tài nguyên )

Để kiểm tra tài nguyên hệ thống và xác định các tiến trình sử dụng nhiều tài nguyên, bạn có thể sử dụng các công cụ dòng lệnh có sẵn trên hệ thống Linux, chẳng hạn như `top`, `htop`, và `ps`. Dưới đây là cách sử dụng các công cụ này:

1. **top**: `top` là một công cụ giám sát tài nguyên mạnh mẽ. Bạn có thể chạy nó bằng cách nhập lệnh sau trong terminal:
    
    ```
    top
    
    ```
    
    Sau đó, `top` sẽ hiển thị danh sách các tiến trình đang chạy, sắp xếp theo mức độ sử dụng CPU mặc định. Bạn có thể sử dụng các phím tắt để sắp xếp lại dự liệu, nhấn `Shift+M` để sắp xếp theo mức độ sử dụng bộ nhớ.
    
2. **htop**: `htop` là một phiên bản nâng cấp của `top` với giao diện tương tác và nhiều tính năng tiện ích. Để sử dụng `htop`, bạn có thể cài đặt nó (nếu chưa có) và chạy lệnh sau:
    
    ```
    sudo apt-get install htop  # Nếu bạn sử dụng Ubuntu hoặc Debian
    sudo yum install htop      # Nếu bạn sử dụng CentOS hoặc Red Hat
    htop
    
    ```
    
    `htop` cho phép bạn dễ dàng tương tác với danh sách tiến trình, tìm kiếm và sắp xếp chúng theo nhiều cách khác nhau.
    
3. **ps**: Lệnh `ps` cho phép bạn liệt kê danh sách tiến trình. Để liệt kê tất cả tiến trình đang chạy, sử dụng lệnh sau:
    
    ```
    ps aux
    
    ```
    
    Điều này sẽ hiển thị danh sách tất cả tiến trình với thông tin về CPU, bộ nhớ và nhiều thông tin khác. Bạn có thể sử dụng các lựa chọn của `ps` để định dạng và lọc kết quả theo cách bạn muốn.
    

Sử dụng các công cụ này, bạn có thể xác định các tiến trình tiêu thụ nhiều tài nguyên (CPU, bộ nhớ) và có thể xem chi tiết về từng tiến trình để tìm hiểu nguyên nhân của sự tiêu thụ tài nguyên cao. Sau đó, bạn có thể quyết định các biện pháp cần thực hiện, chẳng hạn như tối ưu hóa tiến trình hoặc tăng tài nguyên hệ thống.