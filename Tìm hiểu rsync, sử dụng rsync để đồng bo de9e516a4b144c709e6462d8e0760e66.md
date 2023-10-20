# Tìm hiểu rsync, sử dụng rsync để đồng bộ các bản backup code, db sang các máy remote

`rsync` là một công cụ dòng lệnh mạnh mẽ cho việc sao chép và đồng bộ hóa dữ liệu giữa các máy tính hoặc máy chủ. Nó có khả năng sao chép dữ liệu cục bộ hoặc từ xa, và nó sử dụng giao thức SSH để bảo vệ dữ liệu trong quá trình truyền tải. Dưới đây là cách sử dụng `rsync` để đồng bộ các bản sao lưu mã nguồn và cơ sở dữ liệu sang các máy chủ từ xa:

**Bản sao lưu mã nguồn WordPress:**

```bash
rsync -avz /path/to/local/backup/folder/ user@remote-server:/path/to/remote/backup/folder/

```

- `a`: Chế độ archive, bảo đảm rằng tất cả các quyền, thời gian sửa đổi và đặc điểm của tệp tin được bảo tồn.
- `v`: Hiển thị thông tin về quá trình sao chép.
- `z`: Nén dữ liệu trong quá trình truyền tải để tiết kiệm băng thông.
- `/path/to/local/backup/folder/`: Đường dẫn đến thư mục sao lưu cục bộ.
- `user`: Tên người dùng SSH trên máy chủ từ xa.
- `remote-server`: Địa chỉ hoặc tên máy chủ từ xa.
- `/path/to/remote/backup/folder/`: Đường dẫn đến thư mục sao lưu trên máy chủ từ xa.

**Bản sao lưu cơ sở dữ liệu MySQL:**

Để sao chép và đồng bộ hóa cơ sở dữ liệu MySQL, bạn có thể sử dụng lệnh `mysqldump` và sau đó sử dụng `rsync` để sao chép tệp sao lưu:

```bash
mysqldump -u your_db_user -p your_db_name > /path/to/local/db_backup.sql
rsync -avz /path/to/local/db_backup.sql user@remote-server:/path/to/remote/db_backup.sql

```

- `mysqldump -u your_db_user -p your_db_name > /path/to/local/db_backup.sql`: Tạo một tệp sao lưu của cơ sở dữ liệu MySQL.
- `/path/to/local/db_backup.sql`: Đường dẫn đến tệp sao lưu cơ sở dữ liệu cục bộ.
- `user`: Tên người dùng SSH trên máy chủ từ xa.
- `remote-server`: Địa chỉ hoặc tên máy chủ từ xa.
- `/path/to/remote/db_backup.sql`: Đường dẫn đến tệp sao lưu cơ sở dữ liệu trên máy chủ từ xa.

Với các lệnh trên, bạn có thể tự động đồng bộ hóa các bản sao lưu của mã nguồn và cơ sở dữ liệu từ máy chủ cục bộ sang máy chủ từ xa. Hãy thay đổi các đường dẫn và thông tin xác thực cho phù hợp với môi trường của bạn.