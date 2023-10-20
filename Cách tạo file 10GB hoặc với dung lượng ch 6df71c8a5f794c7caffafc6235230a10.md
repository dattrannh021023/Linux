# Cách tạo file 10GB hoặc với dung lượng chỉ định trong Linux

Để tạo một tệp với dung lượng cố định (ví dụ: 10GB) trong Linux, bạn có thể sử dụng một số lệnh hoặc công cụ như `dd` hoặc `fallocate`. Dưới đây là cách sử dụng cả hai cách:

**Sử dụng lệnh `dd`**:

Bạn có thể sử dụng lệnh `dd` để tạo một tệp với dung lượng cố định. Dưới đây là ví dụ để tạo một tệp 10GB:

```bash
dd if=/dev/zero of=largefile bs=1M count=10240

```

- `if`: Đây là đầu vào, trong trường hợp này, `/dev/zero` là nguồn dữ liệu gốc.
- `of`: Đây là đầu ra, tên của tệp bạn muốn tạo (ví dụ: `largefile`).
- `bs`: Kích thước khối, ở đây đang sử dụng 1MB.
- `count`: Số lượng khối, ở đây đang sử dụng 10,240 khối để tạo một tệp 10GB.

**Sử dụng lệnh `fallocate`**:

Lệnh `fallocate` là một cách nhanh chóng để tạo một tệp với dung lượng cố định mà không cần thực sự ghi dữ liệu vào tệp. Dưới đây là cách sử dụng `fallocate` để tạo một tệp 10GB:

```bash
fallocate -l 10G largefile

```

- `l`: Đây là tùy chọn để chỉ định dung lượng của tệp.

Bất kỳ trong hai phương pháp trên đều có thể tạo một tệp với dung lượng xác định. Chọn phương pháp phù hợp với nhu cầu của bạn.