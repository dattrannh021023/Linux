# tọa script tự động restart service khi service bị down

Để tạo một script tự động khởi động lại một dịch vụ khi dịch vụ bị ngừng hoạt động, bạn có thể sử dụng một tập lệnh như Bash. Dưới đây là một ví dụ về cách tạo một script tự động khởi động lại dịch vụ khi dịch vụ ngừng:

```bash
#!/bin/bash

SERVICE_NAME="tên_dịch_vụ"  # Thay thế bằng tên dịch vụ của bạn

# Hàm kiểm tra trạng thái dịch vụ
check_service_status() {
    if systemctl is-active --quiet $SERVICE_NAME; then
        echo "$SERVICE_NAME is running."
        return 0
    else
        echo "$SERVICE_NAME is not running."
        return 1
    fi
}

# Khởi động lại dịch vụ nếu dịch vụ đã dừng
restart_service_if_stopped() {
    if ! check_service_status; then
        echo "Restarting $SERVICE_NAME..."
        systemctl start $SERVICE_NAME
        check_service_status
    fi
}

# Kiểm tra và khởi động lại dịch vụ
restart_service_if_stopped

```

Hãy thay thế `"tên_dịch_vụ"` bằng tên của dịch vụ bạn muốn theo dõi và khởi động lại. Sau đó, lưu script với một tên và đặt quyền thực thi cho nó (sử dụng `chmod +x script_name.sh`).

Cách script hoạt động:

1. Nó sẽ kiểm tra trạng thái của dịch vụ sử dụng `systemctl is-active`.
2. Nếu dịch vụ đang chạy, nó sẽ thông báo và không làm gì cả.
3. Nếu dịch vụ không hoạt động, nó sẽ khởi động lại dịch vụ bằng lệnh `systemctl start`.

Để sử dụng script này, bạn có thể đặt nó trong một cron job để kiểm tra và khởi động lại dịch vụ theo một lịch trình cụ thể, hoặc bạn có thể chạy nó thủ công khi cần thiết.