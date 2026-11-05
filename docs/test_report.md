# BÁO CÁO KIỂM THỬ VÀ ĐÁNH GIÁ TRƯỚC BÀN GIAO

## 1. Thông tin chung

| Thông tin | Chi tiết |
|---|---|
| Tên dự án | Portfolio CV cá nhân — Vũ Đức Huy |
| Phiên bản tham chiếu | v1.0.0 (theo `docs/RELEASENOTE.md`) |
| Ngày đánh giá | 05/11/2026 |
| Người thực hiện | Trợ lý AI — rà soát tĩnh và kiểm tra giao diện bằng Microsoft Edge |
| Phạm vi | Repository hiện tại: HTML, CSS, README, release note và tài liệu liên quan |
| Phương pháp | Đối chiếu yêu cầu, rà soát tĩnh và chụp trang bằng Microsoft Edge headless ở ba kích thước viewport |
| Môi trường kiểm thử | Windows; Microsoft Edge headless, trang HTML mở cục bộ; Docker chưa kiểm thử |

> **Lưu ý:** Ảnh responsive là ảnh chụp trang trong trình duyệt ở các kích thước viewport chỉ định, không phải ảnh chụp thiết bị vật lý. Chưa thực hiện kiểm thử chéo nhiều trình duyệt, kiểm thử cảm ứng hoặc đo đạc hiệu năng.

### Quy ước trạng thái

- **Đạt:** Có thể xác nhận từ mã nguồn hoặc tài liệu đã kiểm tra.
- **Chưa đạt:** Đã phát hiện lỗi hoặc nội dung chưa đáp ứng mong đợi.
- **Cần cải thiện:** Chưa có đủ bằng chứng kiểm thử, hoặc cần kiểm tra/bổ sung trước khi kết luận.

## 2. Bảng tổng quan trạng thái

| # | Nhóm tiêu chí | Trạng thái | Tóm tắt |
|---:|---|---|---|
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | Chưa đạt | Có các mục nội dung và điều hướng chính; một số liên kết chưa hoạt động đúng như mong đợi. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | Cần cải thiện | Đã chụp và kiểm tra trang tại viewport mobile, tablet, desktop; chưa kiểm thử trên thiết bị vật lý hoặc nhiều trình duyệt. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | Đây là trang tĩnh; chưa có kết quả chạy thử, đo hiệu năng hoặc kiểm tra lỗi tải tài nguyên. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Cần cải thiện | Không thấy cấu hình bí mật cần thiết trong tài liệu đã rà soát; chưa thực hiện kiểm thử bảo mật chuyên biệt. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Chưa đạt | Phát hiện lỗi markup, thông tin nhận diện không nhất quán và đường dẫn cây thư mục trong README chưa khớp. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Cần cải thiện | Đã có ảnh responsive; chưa xác nhận lệnh Docker, chưa có kiểm thử tự động hoặc minh chứng triển khai. |

## 3. Nội dung chi tiết theo tiêu chí

### 3.1. Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ có trong trang | Đạt | Nội dung và các section tương ứng có trong `index.html`. |
| Điều hướng nội bộ tới các section | Đạt | Có các anchor `#about`, `#skills`, `#projects`, `#contact`; cần xác nhận thao tác thực tế trên trình duyệt. |
| Liên kết xem chi tiết dự án | Chưa đạt | Các nút “Xem chi tiết” hiện dùng `href="#"`, chưa dẫn tới trang hoặc tài nguyên dự án. |
| Liên kết email và hồ sơ liên hệ | Chưa đạt | Email hiển thị địa chỉ liên hệ nhưng liên kết mở hộp thư Gmail chung; liên kết GitHub trỏ tới trang chủ thay vì hồ sơ cụ thể; nhãn LinkedIn lại trỏ tới Facebook. |
| Nội dung nhận diện cá nhân thống nhất | Chưa đạt | Tiêu đề tab và chân trang ghi “Nguyễn Văn An”, trong khi nội dung giới thiệu và README ghi “Vũ Đức Huy”. Thẻ tác giả có cách viết hoa không thống nhất. |
| Ảnh trong thẻ dự án đầu tiên có markup hợp lệ | Chưa đạt | Thẻ `<img>` đầu tiên trong danh sách dự án không có phần kết thúc `>` trước phần tử `.card-body`; cần sửa và kiểm tra lại HTML. |

### 3.2. Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Có khai báo viewport cho thiết bị di động | Đạt | `index.html` có thẻ `meta viewport`. |
| CSS có bố cục responsive | Đạt | `assets/css/styles.css` dùng hướng mobile-first, breakpoint từ 768px và 1280px, cùng Flexbox/CSS Grid. |
| Có trạng thái focus hỗ trợ điều hướng bàn phím | Đạt | CSS có trạng thái `:focus-visible` cho liên kết/nút. Chưa thực hiện kiểm thử bàn phím từ đầu đến cuối. |
| Có xét tùy chọn giảm chuyển động | Đạt | CSS có quy tắc `prefers-reduced-motion`. Chưa xác nhận trực quan trên trình duyệt. |
| Hiển thị trang ở viewport mobile (390 × 844) | Đạt | Đã mở trang trong trình duyệt, kiểm tra giao diện trong viewport và chụp ảnh màn hình: [responsive-mobile.png](screenshots/responsive-mobile.png). |
| Hiển thị trang ở viewport tablet (768 × 1024) | Đạt | Đã mở trang trong trình duyệt, kiểm tra giao diện trong viewport và chụp ảnh màn hình: [responsive-tablet.png](screenshots/responsive-tablet.png). |
| Hiển thị trang ở viewport desktop (1440 × 1000) | Đạt | Đã mở trang trong trình duyệt, kiểm tra giao diện trong viewport và chụp ảnh màn hình: [responsive-desktop.png](screenshots/responsive-desktop.png). |
| Khả năng tương thích trên thiết bị và trình duyệt khác | Cần cải thiện | Chưa kiểm thử trên thiết bị vật lý hoặc đối chiếu Chrome, Firefox, Edge và Safari; ảnh chụp viewport không thay thế kiểm thử chéo trình duyệt. |
| Văn bản thay thế cho ảnh và khả năng tiếp cận | Cần cải thiện | Ảnh đại diện và các ảnh dự án phía sau có `alt`; ảnh dự án đầu tiên chưa có `alt` hợp lệ do markup chưa hoàn chỉnh. Cần kiểm tra lại và đánh giá bằng trình đọc màn hình. |

### 3.3. Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Trang có thể được phục vụ như website tĩnh | Đạt | Repository có `index.html` và CSS tách riêng; README hướng dẫn dùng Python HTTP server hoặc Nginx. Chưa chạy thử các lệnh này. |
| Hành vi khi thiếu kết nối hoặc ảnh ngoài không tải được | Cần cải thiện | Ảnh dự án lấy từ URL bên ngoài; chưa kiểm tra khi mất mạng, URL lỗi hoặc máy chủ ảnh không phản hồi. |
| Xử lý lỗi phía ứng dụng | Cần cải thiện | Không có backend hoặc luồng xử lý dữ liệu trong phạm vi rà soát; chưa có kịch bản lỗi và kết quả vận hành thực tế để đánh giá. |
| Hiệu năng tải trang | Cần cải thiện | Chưa đo thời gian tải, kích thước tài nguyên, chỉ số Lighthouse/Core Web Vitals hoặc hiệu năng trên mạng chậm. |
| Cấu hình log và theo dõi lỗi khi vận hành | Cần cải thiện | Chưa thấy cấu hình giám sát hoặc thu thập lỗi; cần quyết định theo môi trường triển khai nếu đây là yêu cầu bàn giao. |

### 3.4. Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Nhu cầu cấu hình môi trường và thông tin bí mật | Đạt | README mô tả dự án không cần `.env`, backend hoặc thông số bí mật; website là trang tĩnh. Đây là rà soát tài liệu, không thay thế quét bí mật tự động. |
| Dữ liệu người dùng và biểu mẫu gửi thông tin | Đạt | README nêu rõ hiện không có backend hoặc biểu mẫu gửi liên hệ. Chưa có luồng nhập liệu để kiểm thử. |
| Tài nguyên và liên kết của bên thứ ba | Cần cải thiện | Ảnh được tải từ máy chủ bên ngoài; cần xác nhận nguồn, cân nhắc lưu tài nguyên cục bộ và đánh giá ảnh hưởng quyền riêng tư/khả dụng. |
| Quét lỗ hổng, cấu hình triển khai và bảo mật trình duyệt | Cần cải thiện | Chưa chạy công cụ quét bảo mật; chưa rà soát header bảo mật, chính sách CSP hoặc cấu hình hosting thực tế. |

### 3.5. Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Cấu trúc tách HTML, CSS và hình ảnh | Đạt | Có `index.html`, `assets/css/styles.css` và `assets/img/images.jpg`. |
| Tính hợp lệ và nhất quán của HTML | Chưa đạt | Thẻ ảnh dự án đầu tiên chưa đóng đúng; tiêu đề trang, tác giả và chân trang chưa nhất quán với tên dự án. Chưa chạy HTML validator. |
| Cây thư mục trong README khớp repository | Chưa đạt | README liệt kê release note ở `assets/docs/RELEASENOTE.md`, trong khi tệp thực tế nằm ở `docs/RELEASENOTE.md`. |
| Tài liệu mô tả cách cài đặt và chạy | Đạt | `README.md` có hướng dẫn cho Windows, macOS, Linux và Docker; các lệnh chưa được xác minh bằng chạy thử trong lần đánh giá này. |
| Release note và nhật ký thay đổi | Đạt | Có `docs/RELEASENOTE.md` và `docs/AI_LOG.md`; cần tiếp tục cập nhật khi có thay đổi lớn. |
| Quy trình kiểm tra chất lượng mã | Cần cải thiện | Chưa thấy cấu hình test tự động, lint hoặc CI trong repository; cần xác nhận đây có phải tiêu chí bàn giao của dự án hay không. |

### 3.6. Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú / Minh chứng |
|---|---|---|
| Hướng dẫn triển khai/chạy cục bộ | Đạt | README có lệnh Python HTTP server và hướng dẫn Live Server; chưa thực thi để xác nhận cổng và đường dẫn. |
| Hướng dẫn chạy bằng Docker | Cần cải thiện | README hướng dẫn mount thư mục vào image `nginx:alpine`; chưa chạy Docker để kiểm tra cú pháp, ánh xạ cổng và khả năng truy cập. |
| Bộ kiểm thử và kết quả kiểm thử | Cần cải thiện | Chưa có test suite hoặc log chạy kiểm thử kèm theo báo cáo này. |
| Minh chứng trực quan responsive | Đạt | Đã lưu ảnh chụp viewport mobile, tablet và desktop tại `docs/screenshots/`; liên kết ảnh được đính kèm trong mục 3.2. |
| Kiểm thử trên hệ điều hành/trình duyệt mục tiêu | Cần cải thiện | Chưa thực hiện kiểm thử chéo Windows, macOS, Linux; chưa xác nhận kết quả trên các trình duyệt khác nhau. |

## 4. Đánh giá tổng kết và đề xuất

### Nhận định chung

Dự án có phạm vi phù hợp với một portfolio tĩnh đơn giản: cấu trúc trang, nội dung chính, CSS responsive và hướng dẫn chạy đã được chuẩn bị. Tuy nhiên, qua rà soát tĩnh phát hiện lỗi markup, một số liên kết chưa hoàn thiện, thông tin nhận diện chưa nhất quán và sai khác giữa cây thư mục trong README với repository. Các lệnh chạy và hiển thị thực tế cũng chưa được xác nhận.

**Kết luận:** Chưa nên xác nhận bàn giao cuối cùng cho tới khi xử lý các mục **Chưa đạt** và thực hiện kiểm thử trình duyệt/triển khai tối thiểu. Đây là đánh giá dựa trên mã nguồn và tài liệu; không phải chứng nhận bảo mật hay kết quả kiểm thử trên mọi môi trường.

### Đề xuất ưu tiên trước khi bàn giao

1. Sửa markup của ảnh dự án đầu tiên; chạy HTML validator và xử lý các lỗi được báo.
2. Đồng bộ tên dự án/người sở hữu ở tiêu đề trang, metadata tác giả và chân trang.
3. Thay `href="#"` bằng URL dự án thật hoặc bỏ liên kết nếu dự án chưa có trang đích.
4. Cập nhật các liên kết email, GitHub và mạng xã hội để nhãn, nội dung và URL cùng trỏ đúng đích.
5. Sửa cây thư mục trong README để phản ánh đúng vị trí `docs/RELEASENOTE.md`.
6. Chạy thử trên trình duyệt ở ít nhất một kích thước di động và một kích thước desktop; xác nhận điều hướng, tải CSS/ảnh và liên kết.
7. Chạy thử các hướng dẫn Python và Docker nếu đây là phương thức triển khai bàn giao; lưu lại lệnh và kết quả.
8. Đính kèm ảnh chụp màn hình hoặc log kiểm thử; cân nhắc kiểm tra hiệu năng và quét bảo mật phù hợp với môi trường triển khai.

## 5. Kết quả kiểm thử bổ sung

| Nội dung | Kết quả |
|---|---|
| Rà soát tĩnh HTML/CSS/tài liệu | Đã thực hiện; phát hiện các vấn đề được liệt kê trong báo cáo. |
| Mở trang trong trình duyệt | Đã thực hiện với tệp HTML cục bộ bằng Microsoft Edge headless; đã kiểm tra nội dung hiển thị và chụp ảnh ở ba kích thước viewport. Chưa kiểm tra máy chủ HTTP. |
| Chụp ảnh responsive | Đã thực hiện: 390 × 844, 768 × 1024 và 1440 × 1000; ảnh lưu trong `docs/screenshots/`. |
| Kiểm thử Docker | Chưa thực hiện. |
| Đo hiệu năng | Chưa thực hiện. |
| Quét bảo mật tự động | Chưa thực hiện. |
| Kiểm tra định dạng Markdown | Đã rà soát nội dung và khoảng trắng cuối dòng; chưa chạy Markdown linter. |
