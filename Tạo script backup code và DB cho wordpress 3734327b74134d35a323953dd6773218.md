# Tạo script backup code và DB cho wordpress

Để tạo một tập lệnh để sao lưu mã nguồn và cơ sở dữ liệu của một trang web WordPress, bạn có thể sử dụng một script shell. Dưới đây là một ví dụ về cách tạo một script shell để sao lưu code và cơ sở dữ liệu:

```bash
#!/bin/bash

# Thiết lập các biến
BACKUP_DIR="/path/to/backup/folder"
WP_DIR="/path/to/wordpress/installation"
DB_USER="your_db_user"
DB_PASS="your_db_password"
DB_NAME="your_db_name"

# Tạo thư mục sao lưu
mkdir -p $BACKUP_DIR

# Sao lưu mã nguồn
tar czf $BACKUP_DIR/wordpress-$(date +"%Y%m%d%H%M%S").tar.gz -C $WP_DIR .

# Sao lưu cơ sở dữ liệu
mysqldump -u $DB_USER -p$DB_PASS $DB_NAME > $BACKUP_DIR/database-$(date +"%Y%m%d%H%M%S").sql

# Nén tệp sao lưu cơ sở dữ liệu
gzip $BACKUP_DIR/database-$(date +"%Y%m%d%H%M%S").sql

echo "Sao lưu hoàn tất."

```

Hãy lưu ý rằng bạn cần điều chỉnh các biến trong script để phù hợp với môi trường cụ thể của bạn. Cụ thể:

- `BACKUP_DIR`: Đây là đường dẫn đến thư mục lưu trữ tệp sao lưu.
- `WP_DIR`: Đây là đường dẫn đến thư mục cài đặt WordPress.
- `DB_USER`: Tên người dùng cơ sở dữ liệu.
- `DB_PASS`: Mật khẩu cơ sở dữ liệu.
- `DB_NAME`: Tên cơ sở dữ liệu WordPress.

Sau khi bạn đã cấu hình script theo nhu cầu của bạn, lưu nó dưới dạng tệp văn bản với đuôi `.sh` (ví dụ: `backup_wordpress.sh`). Đảm bảo bạn đã cấp quyền thực thi cho tệp script bằng lệnh `chmod +x backup_wordpress.sh`.

Sử dụng script này, bạn có thể tự động tạo sao lưu của mã nguồn và cơ sở dữ liệu của trang web WordPress bằng cách chạy tệp script. Sử dụng cron job hoặc lên lịch để tự động chạy script theo thời gian hoặc ngày cụ thể để đảm bảo bạn luôn có sao lưu mới nhất.