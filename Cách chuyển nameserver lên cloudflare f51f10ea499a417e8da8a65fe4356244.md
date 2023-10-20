# Cách chuyển nameserver lên cloudflare

Để chuyển Nameserver lên Cloudflare, bạn cần thực hiện các bước sau:

**Bước 1: Đăng ký tài khoản Cloudflare**

Nếu bạn chưa có tài khoản Cloudflare, hãy đăng ký tài khoản trên trang web của họ.

**Bước 2: Thêm trang web vào Cloudflare**

1. Đăng nhập vào tài khoản Cloudflare của bạn.
2. Bấm vào nút "Add a Site" (Thêm trang web) để bắt đầu quá trình thêm trang web của bạn.
3. Nhập tên miền của bạn và bấm "Add Site" để tiếp tục.

**Bước 3: Chọn gói dịch vụ**

Cloudflare cung cấp nhiều gói dịch vụ khác nhau, bao gồm cả gói miễn phí. Chọn gói dịch vụ phù hợp với nhu cầu của bạn.

**Bước 4: Xác minh danh sách DNS**

Sau khi bạn đã chọn gói dịch vụ, Cloudflare sẽ tự động kiểm tra danh sách DNS của tên miền của bạn. Đảm bảo rằng các bản ghi DNS của bạn đã được sao lưu đúng. Bấm "Next" để tiếp tục.

**Bước 5: Chỉnh sửa Nameserver**

Cloudflare sẽ cung cấp hai Nameserver của họ. Bạn cần thay đổi Nameserver của tên miền của bạn để trỏ đến Nameserver của Cloudflare.

1. Đăng nhập vào tài khoản quản lý tên miền của bạn (nơi bạn đã mua tên miền).
2. Tìm và truy cập cài đặt Nameserver hoặc DNS của tên miền.
3. Thay đổi Nameserver của tên miền thành Nameserver mà Cloudflare đã cung cấp.
    
    Ví dụ:
    
    - Nameserver 1: `your_domain.ns.cloudflare.com`
    - Nameserver 2: `your_domain.ns.cloudflare.com`
4. Lưu thay đổi và chờ đợi quá trình lan truyền trên Internet. Thời gian lan truyền có thể mất vài giờ hoặc thậm chí vài ngày. Trong thời gian này, trang web của bạn vẫn hoạt động như trước.

**Bước 6: Xác minh và hoàn tất cấu hình**

Quay lại trang web Cloudflare và bấm "Done, check nameservers" (Hoàn tất, kiểm tra nameserver). Cloudflare sẽ kiểm tra xem Nameserver của bạn đã được cài đặt đúng chưa.

**Bước 7: Cấu hình trang web**

Bây giờ bạn có thể cấu hình trang web của bạn trong bảng điều khiển Cloudflare, bao gồm cài đặt bảo mật, tối ưu hóa hiệu suất, và quản lý bộ lọc bảo vệ.

Cloudflare cung cấp một loạt tài liệu hướng dẫn chi tiết và tài liệu hỗ trợ để bạn có thể tận dụng toàn bộ tính năng của họ.