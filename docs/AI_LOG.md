# Nhật ký thay đổi

Ghi lại tại đây những thay đổi lớn ảnh hưởng đến chức năng, giao diện, kiến trúc, cấu hình, cách cài đặt/chạy hoặc tài liệu quan trọng của dự án. Không cần ghi các chỉnh sửa nhỏ như sửa lỗi chính tả hay định dạng.

Mỗi lần có thay đổi lớn, thêm một mục mới lên đầu nhật ký theo mẫu:

```text
## YYYY-MM-DD — Tên thay đổi
- Nội dung: ...
- Ảnh hưởng: ...
- Kiểm tra: ...
```

## 2026-11-05 — Bổ sung tài liệu hướng dẫn dự án

- **Nội dung:** Tạo README tiếng Việt mô tả dự án portfolio, chức năng, công nghệ, yêu cầu môi trường, cài đặt, cấu hình và thông tin liên hệ.
- **Hướng dẫn chạy:** Bổ sung cách chạy cục bộ trên Windows, macOS, Linux và cách chạy bằng Docker với Nginx.
- **Ảnh hưởng:** Giúp người dùng hiểu, thiết lập và xem trước website mà không cần framework hay bước biên dịch.
- **Kiểm tra:** Kiểm tra định dạng README bằng `git diff --check`; không phát hiện lỗi khoảng trắng.