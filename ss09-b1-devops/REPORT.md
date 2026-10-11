# SESSION 09 – BÀI 1: KIỂM TRA DOCKER ENGINE VÀ CHẠY HELLO-WORLD

## 1. Mục tiêu

- Kiểm tra Docker CLI và khả năng kết nối Docker Daemon.
- Chạy Docker trên Ubuntu (WSL 2) mà không cần `sudo`.
- Khởi chạy thành công container `hello-world`.

## 2. Môi trường thực hành

| Thành phần | Thông tin |
|---|---|
| Hệ điều hành máy chủ | Windows 11 |
| Môi trường Linux | Ubuntu trên WSL 2 |
| Tài khoản Linux | `devops-hongky` |
| Docker | Docker Desktop, bật WSL Integration |
| Terminal | Ubuntu WSL |

## 3. Các bước thực hiện và kết quả

### 3.1. Kiểm tra phiên bản Docker

**Lệnh:**

```bash
docker version
```

**Kết quả:** Cần dán đầu ra thực tế của lệnh `docker version` tại đây, bao gồm cả phần `Client` và `Server`.

### 3.2. Kiểm tra Docker Daemon

**Lệnh:**

```bash
docker info
```

**Kết quả:** Cần dán đầu ra thực tế của lệnh `docker info` tại đây. Lệnh phải thực thi thành công mà không cần `sudo`.

### 3.3. Chạy container Hello-World

**Lệnh:**

```bash
docker run hello-world
```

**Kết quả quan sát được trên Terminal:**

```text
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4f55086f7dd0: Pull complete
d5e71e64b2f5: Download complete
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
```

Docker đã tải image `hello-world:latest` từ Docker Hub, khởi tạo container và hiển thị thông báo thành công.

## 4. Đánh giá kết quả

| Tiêu chí | Trạng thái |
|---|---|
| Chạy `docker version` | Chờ bổ sung kết quả thực tế |
| Chạy `docker info` | Chờ bổ sung kết quả thực tế |
| Chạy `docker run hello-world` | Đạt |
| Docker hoạt động không cần `sudo` | Đạt đối với lệnh `docker run hello-world` |
| Xuất hiện `Hello from Docker!` | Đạt |

## 5. Kết luận

Đã chạy thành công container `hello-world` trên Ubuntu WSL 2 thông qua Docker Desktop WSL Integration, không cần sử dụng `sudo`. Docker CLI kết nối được tới Docker Daemon, image được tải về và container thực thi thành công.

Cần bổ sung kết quả của `docker version` và `docker info` để hoàn thiện đầy đủ minh chứng theo yêu cầu bài tập.

## 6. Hướng dẫn bổ sung minh chứng

Trong Terminal Ubuntu, chạy lần lượt hai lệnh:

```bash
docker version
docker info
```

Sao chép đầu ra thực tế của hai lệnh vào mục 3.1 và 3.2, sau đó cập nhật trạng thái tương ứng trong bảng đánh giá.