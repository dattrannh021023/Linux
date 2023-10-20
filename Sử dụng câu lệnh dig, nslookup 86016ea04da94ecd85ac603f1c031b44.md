# Sử dụng câu lệnh dig, nslookup

`dig` và `nslookup` là hai công cụ dòng lệnh sử dụng để truy vấn thông tin DNS (Domain Name System). Dưới đây là cách sử dụng các công cụ này:

**Sử dụng câu lệnh dig**:

Cú pháp cơ bản của `dig` là:

```
dig [tùy_chọn] tên_miền

```

Ví dụ 1: Để tìm địa chỉ IP (A record) của tên miền [example.com](http://example.com/), bạn có thể chạy lệnh sau:

```
dig example.com

```

Ví dụ 2: Để tìm thông tin về bản ghi MX (Mail Exchanger) của tên miền [example.com](http://example.com/), bạn có thể sử dụng tùy chọn `-t` như sau:

```
dig -t MX example.com

```

**Sử dụng câu lệnh nslookup**:

Cú pháp cơ bản của `nslookup` là:

```
nslookup tên_miền [máy_chủ_DNS]

```

Ví dụ 1: Để tìm địa chỉ IP của tên miền [example.com](http://example.com/), bạn có thể chạy lệnh sau:

```
nslookup example.com

```

Ví dụ 2: Để tìm thông tin về máy chủ DNS của tên miền [example.com](http://example.com/) từ máy chủ DNS cụ thể (vd: 8.8.8.8 - máy chủ DNS của Google), bạn có thể chạy lệnh sau:

```
nslookup example.com 8.8.8.8

```

Cả hai công cụ `dig` và `nslookup` sẽ cung cấp cho bạn thông tin chi tiết về tên miền, bao gồm địa chỉ IP, bản ghi MX, NS, và nhiều thông tin khác. Chúng rất hữu ích trong việc kiểm tra và xác định thông tin về tên miền và hệ thống DNS.