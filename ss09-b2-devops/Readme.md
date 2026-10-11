# Session 09 – Bài 2: Khởi chạy Nginx với Port Mapping

## 1. Mục tiêu
- Khởi chạy Nginx bằng Docker ở chế độ nền.
- Ánh xạ cổng `8080` của máy chủ tới cổng `80` của container.
- Kiểm tra phản hồi HTTP và dọn dẹp container.

## 2. Môi trường thực hành
- Ubuntu trên WSL 2.
- Docker Desktop tích hợp WSL.
- Tài khoản Linux: `devops-hongky`.
- Image: `nginx:alpine`.
- Tên container: `my-web`.

## 3. Các bước thực hiện

### Bước 1: Chạy container

```bash
docker run -d -p 8080:80 --name my-web nginx:alpine
```

Trong đó: `-d` chạy nền, `-p 8080:80` ánh xạ cổng máy chủ/container, `--name` đặt tên container.

### Bước 2: Kiểm tra trạng thái

```bash
docker ps
```

**Kết quả cần xác minh:** container `my-web` ở trạng thái `Up`, hiển thị ánh xạ `0.0.0.0:8080->80/tcp` hoặc tương đương.

### Bước 3: Gửi HTTP request

```bash
curl http://localhost:8080
```

**Kết quả mong đợi:** phản hồi HTML có nội dung:

```html
<h1>Welcome to nginx!</h1>
```

Có thể mở `http://localhost:8080` bằng trình duyệt để kiểm tra.

### Bước 4: Dừng và xóa container

```bash
docker stop my-web && docker rm my-web
```

Kiểm tra sau khi dọn dẹp:

```bash
docker ps -a
```

**Kết quả cần xác minh:** không còn container tên `my-web`.

## 4. Kết quả thực tế

Điền kết quả sau khi chạy lệnh trên máy. Không sử dụng kết quả giả định thay cho bằng chứng thực hành.

- `docker ps` trước khi dọn dẹp: _Chưa bổ sung_.
- `curl http://localhost:8080`: _Chưa bổ sung_.
- `docker ps -a` sau khi dọn dẹp: _Chưa bổ sung_.

## 5. Kết luận

Bài thực hành được xem là hoàn thành khi container Nginx khởi chạy thành công, `curl` trả về trang mặc định có dòng **Welcome to nginx!**, và container `my-web` được dừng, xóa sau thử nghiệm.

## 6. Vị trí nộp bài

`homework/session_09/ex2/README.md`