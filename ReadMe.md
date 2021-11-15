# Chương trình đào tạo Spring Boot phiên bản nâng cấp

# Đầu mục API:

1. Sinh ra 1000 đầu sách sử dụng Java Faker. Ban đâu khi sinh ngẫu nhiên hãy tạo cả BookInventory với amount ngẫu nhiên từ 0 đến 100 quyển sách.
GET: http://localhost:8080/books/fake_data

![image](https://user-images.githubusercontent.com/79953105/141771705-250aee01-1f89-4b22-a446-1994208b2301.png)

2. Liệt kê các đầu sách sắp xếp theo tiêu chí title từ A-Z
GET: http://localhost:8080/books/sort
![image](https://user-images.githubusercontent.com/79953105/141771477-0f118551-7da9-41ee-9bdd-ea67876f8d4b.png)


3. Tìm đầu sách có title chứa keyword nào đó
GET: http://localhost:8080/books/{title}
![image](https://user-images.githubusercontent.com/79953105/141771864-ce675afc-d0e9-431d-bde0-b8fd5156e024.png)


4. Liệt kê các đầu sách hiện đang hết amount = 0;
GET: http://localhost:8080/books/{title}

![image](https://user-images.githubusercontent.com/79953105/141771902-96bf5fd2-ea49-40b4-a517-974ff63f5438.png)

5. Giả lập lệnh mua sách buy_book, mặc định số lượng mua là 1 quyển, nhưng có thể mua nhiều hơn 1 quyển.
GET: http://localhost:8080/books/buy

![image](https://user-images.githubusercontent.com/79953105/141771922-01e2eb61-0038-4412-957a-1c29d3cad379.png)

6. Nếu số lượng mua lớn số lượng sách có trong kho hãy tạo một event để đặt hàng thêm sách nhập về kho.
GET: http://localhost:8080/books/import

# Khó Khăn

7. Hãy tạo một schedule routine cứ 1 phút chạy 1 lần để tìm ra các đầu sách chỉ còn 1 quyển trong kho để tiến hàng nhập hàng bổ xung, số lượng là 5 quyển mỗi lần bổ xung.

8. Dùng Spring Boot AOP để viết một advice ứng với annotation @Benchmark để đo đạc thời gian thực thi các lệnh REST
