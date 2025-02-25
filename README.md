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
``` src/main/java/com/example/securingweb/ ```:
- ``` SecuringWebApplication.java ```: Lớp chính của ứng dụng.
- ``` MvcConfig.java ```: Cấu hình các view controller.
- ``` WebSecurityConfig.java ```: Cấu hình Spring Security.
- ``` User.java ```: Entity JPA cho người dùng.
- ``` UserRepository.java ```: Repository Spring Data JPA cho dữ liệu người dùng.

``` src/main/resources/ ```:
- ``` templates/ ```: Các template Thymeleaf (home.html, hello.html, login.html, admin.html).
- ``` application.properties ```: Cấu hình cơ sở dữ liệu H2.
- ``` data.sql ```: Dữ liệu người dùng ban đầu cho cơ sở dữ liệu H2.

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

## Demo ứng dụng. 
### 1. Truy cập trang chủ:
- Mở trình duyệt và vào ``` http://localhost:8080 ```
- Bạn sẽ thấy trang chào mừng với các liên kết đến /hello và /admin.
  
![image](https://github.com/user-attachments/assets/24dc4ba5-e043-474c-b161-ae5bf67d3e5e)

### 2. Đăng nhập quyền USER
##### Đăng nhập 
- Bạn có thể sử dụng mặc định tên đăng nhập: user, mật khẩu: password đã được thêm vào CSDL
![image](https://github.com/user-attachments/assets/44b2862e-a17b-4614-a02b-a30640ddf13c)

##### Quyền truy cập: Vì đây là quyền user, nên người đăng nhập có thể xem /hello, nhưng sẽ bị từ chối khi vào /admin (403 Forbidden).
###### Xem được /hello
![image](https://github.com/user-attachments/assets/b4307392-e4fe-4172-8f37-be4802f8321b)

###### Bị từ chối khi  /admin
![image](https://github.com/user-attachments/assets/809fa0f7-0c71-4a2c-a066-e15864312706)

### 3. Đăng nhập quyền ADMIN
##### Đăng nhập 
- Bạn có thể sử dụng mặc định tên đăng nhập: admin, mật khẩu: admin đã được thêm vào CSDL
  ![image](https://github.com/user-attachments/assets/8e4ce26a-0aa0-4185-bf57-58fa6ae61784)

##### Quyền truy cập: Có thể xem cả /hello và /admin.
###### Xem được /hello
![image](https://github.com/user-attachments/assets/b4307392-e4fe-4172-8f37-be4802f8321b)

###### Xem được /admin
![image](https://github.com/user-attachments/assets/16ff14a2-b9ea-4def-adc6-866c8a384a1d)

