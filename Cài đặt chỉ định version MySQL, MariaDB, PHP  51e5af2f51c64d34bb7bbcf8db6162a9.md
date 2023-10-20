# Cài đặt chỉ định version MySQL, MariaDB, PHP. Cách kiểm tra version dịch vụ

Để cài đặt một phiên bản cụ thể của MySQL, MariaDB hoặc PHP trên hệ thống Linux, bạn cần biết trước phiên bản bạn muốn sử dụng và sau đó sử dụng các công cụ quản lý gói phù hợp với hệ điều hành của bạn để cài đặt.

Dưới đây là hướng dẫn cách cài đặt và kiểm tra phiên bản của các dịch vụ này trên hệ thống Linux phổ biến như Ubuntu và CentOS:

### Cài đặt và kiểm tra MySQL hoặc MariaDB:

**Trên Ubuntu/Debian**:

1. Cài đặt MySQL hoặc MariaDB bằng lệnh sau:
    - MySQL:
        
        ```bash
        sudo apt update
        sudo apt install mysql-server
        
        ```
        
    - MariaDB:
        
        ```bash
        sudo apt update
        sudo apt install mariadb-server
        
        ```
        
2. Kiểm tra phiên bản MySQL hoặc MariaDB:
    
    ```bash
    mysql --version
    
    ```
    

**Trên CentOS/RHEL**:

1. Cài đặt MySQL hoặc MariaDB bằng lệnh sau:
    - MySQL:
        
        ```bash
        sudo yum install mysql-server
        
        ```
        
    - MariaDB:
        
        ```bash
        sudo yum install mariadb-server
        
        ```
        
2. Khởi động dịch vụ và thiết lập nó tự động khởi động:
    - MySQL:
        
        ```bash
        sudo systemctl start mysqld
        sudo systemctl enable mysqld
        
        ```
        
    - MariaDB:
        
        ```bash
        sudo systemctl start mariadb
        sudo systemctl enable mariadb
        
        ```
        
3. Kiểm tra phiên bản MySQL hoặc MariaDB:
    
    ```bash
    mysql --version
    
    ```
    

### Cài đặt và kiểm tra PHP:

**Trên Ubuntu/Debian**:

1. Cài đặt PHP bằng lệnh sau:
    
    ```bash
    sudo apt update
    sudo apt install php
    
    ```
    
2. Kiểm tra phiên bản PHP:
    
    ```bash
    php --version
    
    ```
    

**Trên CentOS/RHEL**:

1. Cài đặt PHP bằng lệnh sau:
    
    ```bash
    sudo yum install php
    
    ```
    
2. Kiểm tra phiên bản PHP:
    
    ```bash
    php --version
    
    ```
    

Lưu ý rằng phiên bản cụ thể có thể thay đổi theo thời gian và phiên bản của hệ điều hành, vì vậy hãy kiểm tra tài liệu trực tuyến hoặc trang web chính thức của MySQL, MariaDB và PHP để tìm phiên bản mới nhất.

Một khi bạn đã cài đặt các dịch vụ này và kiểm tra phiên bản, bạn có thể bắt đầu sử dụng chúng cho các ứng dụng và dự án của mình.