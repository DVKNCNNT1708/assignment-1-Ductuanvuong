# Known Issues · Buổi 1

Ghi lại lỗi chưa xử lý được hoặc đã xử lý xong.

| STT | Lỗi gặp phải | Lệnh gây lỗi | Cách đã thử | Trạng thái |
|---:|---|---|---|---|
| 1 | Docker daemon ban đầu chưa chạy nên `hello-world`, `docker info` và một phần smoke test thất bại | `docker info`, `docker run --rm hello-world`, `./scripts/collect_session01_evidence.sh` | Mở Docker Desktop bằng `open -a Docker`, sau đó kiểm tra lại daemon | Đã xử lý một phần |
| 2 | Pull image `ultralytics/ultralytics:latest-cpu` bị lỗi I/O khi extract layer | `./scripts/pull_all.sh` | Chạy lại pull sau khi Docker Desktop hoạt động, theo dõi log trong `pull-images-result.txt` | Chưa xử lý xong |
| 3 | Máy gần hết dung lượng nên script ghi log và Docker image bị lỗi `No space left on device` | `./scripts/collect_session01_evidence.sh`, `docker pull ...` | Kiểm tra `df -h`, xác nhận phân vùng dữ liệu còn khoảng 1.2 GiB; cần giải phóng thêm dung lượng rồi chạy lại script | Chưa xử lý xong |
| 4 | Push lên GitHub thất bại do remote HTTPS yêu cầu token hợp lệ | `git push -u origin buoi-01` | Thử push trực tiếp lên `origin`, GitHub trả về `Invalid username or token`; cần đăng nhập lại bằng PAT hoặc chuyển sang SSH | Chưa xử lý xong |
| 5 | Mini-stack Docker Compose ban đầu không bind được cổng `5000` vì macOS `ControlCenter` tự chiếm cổng này | `docker compose -f compose/docker-compose.smoke.yml up -d` | Đổi cổng registry trong `compose/docker-compose.smoke.yml` từ `5000:5000` sang `5001:5000`, cập nhật `scripts/smoke_test.sh`, sau đó chạy lại thành công | Đã xử lý xong |
