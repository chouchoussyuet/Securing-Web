# Securing Web Application with Spring Security
Dự án này là một ứng dụng web đơn giản sử dụng Spring Boot, được bảo mật bằng Spring Security. Ứng dụng sử dụng cơ sở dữ liệu H2 trong bộ nhớ để lưu trữ thông tin người dùng và vai trò. Dự án hỗ trợ hai vai trò: USER và ADMIN, với quyền truy cập dựa trên vai trò cho các đường dẫn cụ thể.

## Tính năng
- Bảo mật các đường dẫn bằng Spring Security.
- Form đăng nhập với tên người dùng và mật khẩu.
- Quyền truy cập theo vai trò:
    + USER: Có thể truy cập /hello.
    + ADMIN: Có thể truy cập cả /hello và /admin.
- Dữ liệu người dùng được lưu trong cơ sở dữ liệu H2 trong bộ nhớ.
- Sử dụng Thymeleaf để hiển thị giao diện.

## Yêu cầu môi trường
- Java 17 hoặc cao hơn 
- Maven 3.5+ (hoặc sử dụng mvnw đi kèm trong dự án).

## Cấu trúc dự án
src/main/java/com/example/securingweb/:
- SecuringWebApplication.java: Lớp chính của ứng dụng.
- MvcConfig.java: Cấu hình các view controller.
- WebSecurityConfig.java: Cấu hình Spring Security.
- User.java: Entity JPA cho người dùng.
- UserRepository.java: Repository Spring Data JPA cho dữ liệu người dùng.

src/main/resources/:
- templates/: Các template Thymeleaf (home.html, hello.html, login.html, admin.html).
- application.properties: Cấu hình cơ sở dữ liệu H2.
- data.sql: Dữ liệu người dùng ban đầu cho cơ sở dữ liệu H2.

## Chạy ứng dụng 
1. Cách 1: Sử dụng Maven:
   ```
   ./mvnw spring-boot:run
   ```
2. Cách 2: Sử dụng file jar
  ```
    java -jar target/securing-web-initial-0.0.1-SNAPSHOT.jar
  ```
Ứng dụng sẽ khởi động tại ``` http://localhost:8080 ```
