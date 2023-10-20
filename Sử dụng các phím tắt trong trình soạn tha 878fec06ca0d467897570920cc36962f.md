# Sử dụng các phím tắt trong trình soạn thảo vi

Trình soạn thảo `vi` là một trình soạn thảo văn bản mạnh mẽ dành cho hệ điều hành Unix và Linux. Nó được điều khiển bằng cách sử dụng phím tắt và lệnh dòng. Dưới đây là một số phím tắt quan trọng trong `vi`:

1. **Chế độ chèn (Insert Mode)**:
    - `i`: Chuyển vào chế độ chèn trước con trỏ văn bản.
    - `I`: Chuyển vào chế độ chèn ở đầu dòng.
    - `a`: Chuyển vào chế độ chèn sau con trỏ văn bản.
    - `A`: Chuyển vào chế độ chèn ở cuối dòng.
2. **Chế độ di chuyển (Normal Mode)**:
    - `h`: Di chuyển con trỏ sang trái.
    - `j`: Di chuyển con trỏ xuống.
    - `k`: Di chuyển con trỏ lên.
    - `l`: Di chuyển con trỏ sang phải.
    - `w`: Di chuyển đến từ tiếp theo.
    - `b`: Di chuyển đến từ trước đó.
    - `0` (số không): Di chuyển đến đầu dòng.
    - `$`: Di chuyển đến cuối dòng.
    - `G`: Di chuyển đến cuối tài liệu.
    - `gg`: Di chuyển đến đầu tài liệu.
3. **Chế độ xóa (Delete Mode)**:
    - `x`: Xóa ký tự dưới con trỏ.
    - `dd`: Xóa dòng hiện tại.
    - `D`: Xóa từ vị trí con trỏ tới cuối dòng.
4. **Lưu và thoát (Save and Quit)**:
    - `:w`: Lưu tài liệu.
    - `:q`: Thoát trình soạn thảo.
    - `:wq` hoặc `:x`: Lưu và thoát.
5. **Chế độ thay thế (Replace Mode)**:
    - `r`: Thay thế ký tự dưới con trỏ bằng ký tự bạn gõ.
    - `R`: Chuyển vào chế độ thay thế liên tục, cho phép bạn thay thế nhiều ký tự liên tiếp.
6. **Chế độ xóa (Cut and Paste)**:
    - `yy`: Sao chép (copy) dòng hiện tại.
    - `p`: Dán (paste) nội dung đã sao chép sau dòng hiện tại.
    - `P`: Dán nội dung đã sao chép trước dòng hiện tại.
7. **Tìm kiếm và thay thế**:
    - `/`: Bắt đầu tìm kiếm. Sau khi nhập từ khóa tìm kiếm, sử dụng `n` để di chuyển đến kết quả tiếp theo.
    - `:s/từ_khóa_cũ/từ_khóa_mới/g`: Thay thế từ khóa cũ bằng từ khóa mới trên toàn tài liệu.
8. **Hủy và phục hồi**:
    - `u`: Hủy thao tác gần đây.
    - `Ctrl + r`: Phục hồi thao tác đã hủy.
9. **Thoát và không lưu (Quit without Saving)**:
    - `:q!`: Thoát mà không lưu thay đổi (nếu bạn không muốn lưu).

Lưu ý rằng `vi` có một học cú pháp mạnh mẽ và có thể tốn thời gian để nắm bắt. Để học và làm quen với `vi`, hãy thực hành thường xuyên và sử dụng các lệnh dòng để tận dụng toàn bộ tiềm năng của trình soạn thảo này.