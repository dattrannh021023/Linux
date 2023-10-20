# Lệnh chattr trong linux để làm gì? Thực hành

Lệnh `chattr` trong Linux được sử dụng để thay đổi thuộc tính của tệp tin hoặc thư mục trên hệ thống tệp. Nó cho phép bạn gắn các thuộc tính đặc biệt, chẳng hạn như "khóa" hoặc "nén," cho các tệp và thư mục để tăng cường tính bảo mật hoặc quản lý dữ liệu. Có một số cờ và tham số có sẵn trong lệnh `chattr`, bao gồm:

- `+` (plus): Thêm một thuộc tính.
- `` (minus): Loại bỏ một thuộc tính.
- `=` (equal): Thiết lập một thuộc tính.

Dưới đây là một số ví dụ về cách sử dụng lệnh `chattr`:

1. **Chặn việc xóa hoặc thay đổi tệp tin**:
    
    ```
    chattr +i filename
    
    ```
    
    Với cờ `+i`, tệp tin sẽ trở thành "khóa" và không thể bị xóa, di chuyển hoặc thay đổi cho đến khi bạn loại bỏ thuộc tính này.
    
2. **Gắn thuộc tính "bảo mật" cho tệp tin**:
    
    ```
    chattr +s filename
    
    ```
    
    Với cờ `+s`, tệp tin sẽ có thuộc tính bảo mật và chỉ có người dùng gốc mới có thể thay đổi nó.
    
3. **Chỉ đọc cho tệp tin**:
    
    ```
    chattr +a filename
    
    ```
    
    Với cờ `+a`, tệp tin sẽ trở thành chỉ đọc và không thể thay đổi nội dung.
    
4. **Nén tệp tin**:
    
    ```
    chattr +c filename
    
    ```
    
    Với cờ `+c`, tệp tin sẽ được nén để tiết kiệm không gian đĩa.
    
5. **Xóa thuộc tính**:
    
    ```
    chattr -i filename
    
    ```
    
    Để xóa một thuộc tính đã được gắn vào một tệp tin hoặc thư mục.
    

Lưu ý rằng việc sử dụng `chattr` đòi hỏi quyền root hoặc quyền quản trị hệ thống, và bạn cần thận trọng khi áp dụng các thay đổi này, đặc biệt là khi gắn thuộc tính "khóa" cho các tệp tin quan trọng, vì nó có thể khiến bạn mất quyền truy cập hoặc quản lý tệp tin đó.