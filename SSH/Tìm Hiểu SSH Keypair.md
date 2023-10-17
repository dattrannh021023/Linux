# Tìm Hiểu SSH Keypair

SSH Key Pair là một phương pháp chuyên nghiệp và hiệu quả để bảo vệ quá trình truy cập vào các hệ thống từ xa. Trong bài viết này, chúng ta sẽ tìm hiểu về SSH Key Pair, cách chúng hoạt động, cách tạo và quản lý chúng, cùng với lợi ích mà chúng mang lại cho bảo mật hệ thống.

## I. SSH Key Pair là gì?

SSH (Secure Shell) là một giao thức mạng được sử dụng để thiết lập kết nối bảo mật giữa hai thiết bị, thường là máy tính và máy chủ từ xa. SSH Key Pair là cặp cặp khóa, bao gồm khóa riêng tư (private key) và khóa công khai (public key), được sử dụng để xác thực và mã hóa dữ liệu trong quá trình kết nối SSH.

## II. Cách SSH Key Pair hoạt động

### 1. Khóa riêng tư (Private Key):

- Khóa riêng tư là một tệp hoặc chuỗi ký tự được lưu trữ trên máy tính cá nhân.
- Đây là phần quan trọng và bí mật của cặp khóa. Không nên chia sẻ hoặc tiết lộ nó cho người khác.
- Dùng để giải mã thông tin được mã hóa bằng khóa công khai.

### 2. Khóa công khai (Public Key):

- Khóa công khai là một tệp hoặc chuỗi ký tự được lưu trữ trên máy chủ hoặc máy chủ từ xa.
- Được chia sẻ rộng rãi và không cần bí mật.
- Dùng để mã hóa thông tin trước khi gửi nó cho máy tính cá nhân, chủ yếu để xác thực.

Khi bạn kết nối với máy chủ từ xa bằng SSH, máy tính cá nhân của bạn sẽ sử dụng khóa riêng tư để chứng thực mình với máy chủ. Máy chủ sẽ kiểm tra xem khóa công khai tương ứng (được lưu trữ trên máy chủ) có khớp với khóa riêng tư hay không. Nếu khớp, quá trình kết nối được thiết lập mà không cần nhập mật khẩu.

## III. Tạo và Quản Lý SSH Key Pair

Để tạo và quản lý SSH Key Pair, bạn cần thực hiện các bước sau:

### 1. Tạo SSH Key Pair:

- Sử dụng lệnh `ssh-keygen` trên máy tính cá nhân để tạo khóa mới.
- Lệnh này sẽ tạo một cặp khóa mới và lưu chúng trên máy tính cá nhân của bạn.

### 2. Sao lưu và Quản lý khóa:

- Sao lưu và lưu trữ khóa riêng tư ở nơi an toàn, không chia sẻ nó với người khác.
- Thêm khóa công khai vào máy chủ từ xa để cho phép xác thực bằng SSH.

### 3. Sử dụng SSH Key Pair:

- Khi kết nối vào máy chủ từ xa, SSH sẽ sử dụng khóa riêng tư của bạn để xác thực bạn.
- Không cần mật khẩu, một kết nối bảo mật sẽ được thiết lập.

## IV. Lợi Ích của SSH Key Pair

- **Bảo Mật Cao:** Khóa riêng tư là bí mật và không dễ dàng bị đánh cắp. Điều này làm tăng tính bảo mật cho hệ thống của bạn.
- **Không cần Mật khẩu:** Giảm đi sự phụ thuộc vào mật khẩu, giúp tránh được các cuộc tấn công dựa trên mật khẩu yếu.
- **Dễ Quản Lý:** Quản lý quá trình kết nối từ xa trở nên dễ dàng và hiệu quả hơn.

# V. LAB

### Bước 1: Mở Terminal

Đầu tiên, mở terminal trên máy tính chạy CentOS 9.

### Bước 2: Tạo SSH Key Pair

Sử dụng lệnh sau để tạo cặp SSH Key Pair:

```bash
ssh-keygen -t rsa -b 2048

```

Hệ thống sẽ yêu cầu bạn lưu khóa riêng tư. Mặc định, nó sẽ lưu trong thư mục `~/.ssh/id_rsa`.

### Bước 3: Sao lưu Khóa Riêng Tư

Sử dụng lệnh `cp` để sao lưu khóa riêng tư vào một vị trí an toàn. Điều này rất quan trọng để đảm bảo bạn không mất đi khóa riêng tư.

```bash
cp ~/.ssh/id_rsa ~/my_backup_folder/

```

### Bước 4: Sao lưu Khóa Công Khai

Sử dụng lệnh `cat` để hiển thị khóa công khai và sau đó sao chép nó để sử dụng sau này.

```bash
cat ~/.ssh/id_rsa.pub

```

Sao chép khóa công khai và lưu lại nó.

### Bước 5: Kết nối vào Máy Chủ từ Xa

Sử dụng khóa riêng tư và lệnh `ssh` để kết nối vào máy chủ từ xa. Thay thế `<username>` và `<server_address>` bằng tên người dùng và địa chỉ máy chủ cụ thể.

```bash
ssh -i ~/.ssh/id_rsa <username>@<server_address>

```

Bạn sẽ được yêu cầu nhập mật khẩu của người dùng từ xa, nhưng không cần phải nhập mật khẩu sau khi bạn đã nhập khóa riêng tư một lần.

### Bước 6: Đăng Nhập vào Máy Chủ

Sau khi xác thực bằng khóa riêng tư, bạn sẽ đăng nhập vào máy chủ từ xa.

### Bước 7: Đăng Xuất

Khi bạn hoàn thành việc làm việc trên máy chủ từ xa, đăng xuất bằng cách sử dụng lệnh `exit`:

```bash
exit

```

### Kết Luận

Trong bài LAB này, bạn đã tạo và sử dụng SSH Key Pair để kết nối vào máy chủ CentOS từ xa mà không cần mật khẩu. SSH Key Pair là một công cụ quan trọng cho việc bảo mật hệ thống và giúp bạn tạo kết nối bảo mật. Đảm bảo bạn sao lưu khóa riêng tư một cách an toàn và không chia sẻ nó với bất kỳ ai khác.