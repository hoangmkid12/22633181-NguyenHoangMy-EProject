🛒 Hệ thống Thương mại Điện tử Microservices

🧩 Giới thiệu

Đây là dự án mô phỏng một hệ thống thương mại điện tử cơ bản được xây dựng theo kiến trúc Microservices.
Mục tiêu của dự án là thể hiện cách thiết kế và triển khai một hệ thống gồm nhiều dịch vụ độc lập, có thể dễ dàng mở rộng, bảo trì và triển khai bằng Docker.

Hệ thống bao gồm các dịch vụ riêng biệt để xử lý các nghiệp vụ chính như:

🔐 Xác thực người dùng

📦 Quản lý sản phẩm

🧾 Quản lý đơn hàng

🔁 Giao tiếp giữa các dịch vụ qua hàng đợi tin nhắn (RabbitMQ)

🏛️ Kiến trúc hệ thống

Dự án được chia thành 4 dịch vụ chính cùng với các thành phần hỗ trợ như sau:

1. 🧭 API Gateway

Là cổng vào duy nhất của toàn bộ hệ thống.

Tiếp nhận request từ client và định tuyến (forward) đến các dịch vụ phù hợp.

Có thể áp dụng cơ chế HTTP Proxy và API Key để xác thực và kiểm soát truy cập.

2. 🔑 Auth Service

Xử lý toàn bộ các nghiệp vụ đăng ký, đăng nhập và xác thực người dùng.

Sử dụng JSON Web Token (JWT) để bảo mật và duy trì phiên đăng nhập.

3. 🛍️ Product Service

Chịu trách nhiệm quản lý sản phẩm, bao gồm:

🆕 Tạo mới sản phẩm

📋 Xem danh sách sản phẩm

Dữ liệu sản phẩm được lưu trữ riêng trong MongoDB.

4. 📦 Order Service

Xử lý các nghiệp vụ tạo đơn hàng, quản lý đơn hàng của người dùng.

Giao tiếp với Product Service để lấy thông tin sản phẩm.

Hỗ trợ RabbitMQ cho việc truyền thông điệp không đồng bộ (asynchronous messaging) giữa các dịch vụ.

💻 Công nghệ sử dụng

Backend:Node.js, Express.js
Database: MongoDB
Kiến trúc: Microservices, API Gateway
Containerization: Docker & Docker Compose
Authentication: JSON Web Token (JWT)
Proxy: HTTP Proxy

5. ⚙️ Thành phần bổ trợ

MongoDB: Lưu trữ dữ liệu cho từng dịch vụ (Auth, Product, Order).

RabbitMQ: Hàng đợi tin nhắn giúp các service giao tiếp không đồng bộ, đảm bảo hệ thống hoạt động mượt mà.

👨‍💻 Tác giả
Nguyễn Hoàng Mỹ
