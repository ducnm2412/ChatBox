# Messenger Lite (Simple Chat Box)

Đồ án Mạng Máy Tính - Hệ thống Chat Mạng Real-time đơn giản.

## 1. Cài đặt môi trường

Chạy lệnh sau để cài các thư viện cần thiết:
pip install -r requirements.txt

## 2. Khởi tạo Database

Chạy script sau 1 lần duy nhất để tạo file chat.db:
python create_db.py

## 3. Cách chạy chương trình

Hệ thống cần chạy 3 thành phần theo thứ tự sau:

- Bước 1: Chạy Microservice (gRPC)\*\*
  python grpc_server.py
- Bước 2: Chạy Main Server\*\*
  python MainServer.py
- Bước 3: Chạy Client (Người dùng)\*\*
  python client_gui.py
  (Có thể mở nhiều terminal để chạy nhiều Client cùng lúc)

## 4. Cấu trúc thư mục

SIMPLE CHAT BOX/
│
├── chat.db # Cơ sở dữ liệu SQLite lưu trữ tin nhắn
├── chat_old.db # CSDL cũ (backup / thử nghiệm)
│
├── client_gui.py # Chương trình Client (giao diện người dùng)
│
├── create_db.py # Script khởi tạo database (chạy 1 lần)
│
├── grpc_server.py # Microservice gRPC xử lý các RPC từ client
│
├── MainServer.py # Server chính, điều phối logic chat và kết nối database
│
├── models.py # Định nghĩa model và các hàm thao tác với database
│
├── service.proto # Định nghĩa giao thức gRPC (RPC, message)
├── service_pb2.py # File sinh tự động từ service.proto (message)
├── service_pb2_grpc.py # File sinh tự động từ service.proto (stub & service)
│
├── requirements.txt # Danh sách thư viện Python cần cài đặt
│
├── README.md # Tài liệu mô tả dự án
