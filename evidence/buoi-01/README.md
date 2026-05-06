# Minh chứng Buổi 1

Thư mục này dùng để nộp minh chứng thiết lập môi trường lab.

## Sinh viên điền thông tin

- Họ tên: Vương Đức Tuấn
- Mã sinh viên: 1771020717
- Nhóm: B4
- Vai trò dự kiến trong nhóm: AI Vision
- Hệ điều hành: macOS arm64 (Darwin 24.6.0)
- Ghi chú: Đã chạy script pull image và collect evidence. Docker Desktop hoạt động nhưng gặp lỗi thiếu dung lượng và lỗi I/O khi pull image lớn.

## Các file minh chứng nên có

- `tool-versions.txt`
- `docker-version.txt`
- `compose-version.txt`
- `hello-world.txt`
- `smoke-test-result.txt`
- `image-list.txt`
- `git-log.txt`
- `checklist.md`
- `known-issues.md`

## Cách sinh file tự động

macOS/Linux:

```bash
./scripts/collect_session01_evidence.sh
```

Windows:

```powershell
.\scripts\collect_session01_evidence.ps1
```
