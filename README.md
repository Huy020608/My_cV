# Portfolio CV cá nhân — Vũ Đức Huy

Website portfolio CV cá nhân giới thiệu thông tin, kỹ năng, dự án và cách liên hệ với Vũ Đức Huy. Trang được xây dựng dưới dạng website tĩnh bằng HTML và CSS, có bố cục responsive để sử dụng trên điện thoại, máy tính bảng và máy tính.

## Chức năng

- Hiển thị phần giới thiệu và vai trò Frontend Developer.
- Trình bày kỹ năng, công nghệ và các dự án tiêu biểu.
- Điều hướng nhanh tới các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Cung cấp thông tin liên hệ và liên kết quay lại đầu trang.
- Tương thích với các kích thước màn hình phổ biến; hỗ trợ điều hướng bằng bàn phím.

> Đây là website tĩnh, hiện chưa có backend, biểu mẫu gửi liên hệ hoặc chức năng quản lý nội dung. Một số ảnh minh họa dự án được tải từ nguồn bên ngoài và cần kết nối Internet để hiển thị.

## Công nghệ sử dụng

- **HTML5**: cấu trúc và nội dung trang.
- **CSS3**: giao diện responsive, Flexbox và CSS Grid.
- **Git và GitHub**: quản lý mã nguồn.
- **Nginx (tùy chọn)**: phục vụ website bằng Docker.

Website không sử dụng framework, không cần trình quản lý gói và không cần biên dịch.

## Yêu cầu môi trường

### Chạy trực tiếp

- Windows, macOS hoặc Linux.
- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Một trong các lựa chọn để phục vụ website cục bộ:
  - Python 3; hoặc
  - Visual Studio Code với tiện ích Live Server.

Có thể mở `index.html` trực tiếp trong trình duyệt, nhưng dùng máy chủ cục bộ được khuyến nghị để có trải nghiệm ổn định hơn.

### Chạy bằng Docker

- Docker Desktop trên Windows/macOS, hoặc Docker Engine trên Linux.
- Docker daemon đang chạy.
- Không cần cài Python, Node.js hay Nginx trên máy; Docker sẽ tải image `nginx:alpine` nếu image chưa có.

## Cài đặt

Clone kho mã nguồn:

```bash
git clone https://github.com/Huy020608/My_cV.git
cd My_cV
```

Nếu không sử dụng Git, tải mã nguồn từ GitHub và giải nén vào một thư mục.

## Cấu hình và tùy chỉnh

Dự án không có bước cấu hình môi trường, không cần file `.env` và không có thông số bí mật.

- Sửa nội dung, thông tin cá nhân, kỹ năng, dự án và liên hệ trong `index.html`.
- Sửa màu sắc, bố cục và kiểu chữ trong `assets/css/styles.css`.
- Thay ảnh đại diện tại `assets/img/images.jpg` hoặc cập nhật đường dẫn ảnh trong `index.html`.
- Các ảnh dự án đang dùng URL bên ngoài; để tự lưu ảnh, thêm tệp vào thư mục `assets/img/` rồi cập nhật thuộc tính `src` tương ứng trong `index.html`.

Khi thay đổi thông tin liên hệ, hãy kiểm tra cả nội dung hiển thị và URL của liên kết để bảo đảm chúng trỏ tới đúng địa chỉ.

## Chạy thử

### Windows

Mở PowerShell tại thư mục dự án. Dùng Python Launcher:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python:

```powershell
python -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

**Hoặc dùng Visual Studio Code:** mở thư mục dự án, cài tiện ích Live Server, nhấp chuột phải vào `index.html` và chọn **Open with Live Server**. Cấu hình hiện tại của dự án đặt cổng Live Server là `5502`.

### macOS

Mở Terminal tại thư mục dự án:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở Terminal tại thư mục dự án:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

Nếu hệ thống chưa cài Python 3, hãy cài Python 3 bằng trình quản lý gói của bản phân phối hoặc dùng Docker theo hướng dẫn bên dưới.

### Docker

Chạy lệnh tại thư mục gốc của dự án để mount mã nguồn chỉ đọc vào Nginx và phục vụ website ở cổng `8080`.

**Windows PowerShell:**

```powershell
docker run --rm -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS hoặc Linux:**

```bash
docker run --rm -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Mở <http://localhost:8080>. Dừng container bằng `Ctrl+C`. Lệnh trên dùng image Nginx chính thức, không yêu cầu Dockerfile hoặc bước build riêng.

## Kiểm tra nhanh

Sau khi chạy máy chủ, xác nhận trang mở được và các mục Giới thiệu, Kỹ năng, Dự án, Liên hệ hiển thị. Kiểm tra giao diện ở cả kích thước màn hình hẹp và rộng. Ảnh dự án lấy từ bên ngoài có thể không xuất hiện nếu mất kết nối Internet hoặc nguồn ảnh thay đổi.

## Cấu trúc dự án

```text
.
├── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── docs/
│   │   └── RELEASENOTE.md
│   └── img/
│       └── images.jpg
└── README.md
```

## Thông tin liên hệ

- **Email:** [vuhuy020608@gmail.com](mailto:vuhuy020608@gmail.com)
- **GitHub:** [Huy020608](https://github.com/Huy020608)
- **Kho mã nguồn:** [Huy020608/My_cV](https://github.com/Huy020608/My_cV)
