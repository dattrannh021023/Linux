# Tìm hiểu Query MySQL

Câu truy vấn (query) MySQL là một cụm lệnh được sử dụng để truy xuất, cập nhật, xóa hoặc thay đổi dữ liệu trong cơ sở dữ liệu MySQL. MySQL sử dụng ngôn ngữ truy vấn SQL (Structured Query Language) để tương tác với cơ sở dữ liệu. Dưới đây là một số ví dụ về cách sử dụng câu truy vấn MySQL:

1. **Truy vấn dữ liệu từ một bảng**:
    
    ```sql
    SELECT column1, column2 FROM table_name WHERE condition;
    
    ```
    
    Ví dụ:
    
    ```sql
    SELECT first_name, last_name FROM employees WHERE department = 'IT';
    
    ```
    
2. **Thêm dữ liệu vào bảng**:
    
    ```sql
    INSERT INTO table_name (column1, column2, column3, ...) VALUES (value1, value2, value3, ...);
    
    ```
    
    Ví dụ:
    
    ```sql
    INSERT INTO products (product_name, price) VALUES ('Laptop', 800);
    
    ```
    
3. **Cập nhật dữ liệu trong bảng**:
    
    ```sql
    UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
    
    ```
    
    Ví dụ:
    
    ```sql
    UPDATE customers SET email = 'newemail@example.com' WHERE customer_id = 1;
    
    ```
    
4. **Xóa dữ liệu từ bảng**:
    
    ```sql
    DELETE FROM table_name WHERE condition;
    
    ```
    
    Ví dụ:
    
    ```sql
    DELETE FROM orders WHERE order_id = 5;
    
    ```
    
5. **Tạo bảng mới**:
    
    ```sql
    CREATE TABLE table_name (
        column1 datatype,
        column2 datatype,
        ...
    );
    
    ```
    
    Ví dụ:
    
    ```sql
    CREATE TABLE employees (
        employee_id INT PRIMARY KEY,
        first_name VARCHAR(50),
        last_name VARCHAR(50),
        department VARCHAR(50)
    );
    
    ```
    
6. **Xóa bảng**:
    
    ```sql
    DROP TABLE table_name;
    
    ```
    
    Ví dụ:
    
    ```sql
    DROP TABLE customers;
    
    ```
    
7. **Điều kiện WHERE**:
    
    Câu truy vấn có thể được lọc sử dụng điều kiện WHERE để chọn các hàng cụ thể mà bạn muốn truy vấn. Ví dụ:
    
    ```sql
    SELECT product_name, price FROM products WHERE price < 100;
    
    ```
    
8. **Sắp xếp kết quả**:
    
    Bạn có thể sắp xếp kết quả bằng cách sử dụng câu lệnh ORDER BY. Ví dụ:
    
    ```sql
    SELECT customer_name, order_date FROM orders ORDER BY order_date DESC;
    
    ```
    
9. **Nhóm và tổng hợp dữ liệu**:
    
    Bạn có thể sử dụng các hàm như SUM, COUNT, AVG để nhóm và tổng hợp dữ liệu. Ví dụ:
    
    ```sql
    SELECT department, AVG(salary) FROM employees GROUP BY department;
    
    ```
    
10. **Kết hợp các bảng**:
    
    Bạn có thể kết hợp các bảng bằng cách sử dụng các câu lệnh JOIN. Ví dụ:
    
    ```sql
    SELECT customers.customer_name, orders.order_date FROM customers
    INNER JOIN orders ON customers.customer_id = orders.customer_id;
    
    ```
    

Câu truy vấn MySQL rất mạnh mẽ và có nhiều tính năng mà bạn có thể tìm hiểu thêm. Điều quan trọng là hiểu cách sử dụng câu truy vấn để tương tác với cơ sở dữ liệu MySQL và đảm bảo an toàn dữ liệu trong quá trình thực hiện các thao tác.