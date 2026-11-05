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
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | GitHub Pages truy cập được, CSS/ảnh tải thành công; chưa đo hiệu năng hoặc kiểm tra tình huống lỗi. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Cần cải thiện | Không thấy cấu hình bí mật cần thiết trong tài liệu đã rà soát; chưa thực hiện kiểm thử bảo mật chuyên biệt. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Chưa đạt | Phát hiện lỗi markup, thông tin nhận diện không nhất quán và đường dẫn cây thư mục trong README chưa khớp. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Cần cải thiện | GitHub Pages và nội dung triển khai đã xác minh; Docker, kiểm thử tự động và video demo chưa có minh chứng. |

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

**Kết luận:** GitHub Pages đã được mở thử và đối chiếu nội dung triển khai với HTML/CSS/ảnh trong repository; tuy vậy, chưa nên xác nhận bàn giao cuối cùng cho tới khi xử lý các mục **Chưa đạt**. Docker, hiệu năng, quét bảo mật và khả năng tương thích trên trình duyệt/thiết bị khác vẫn chưa được kiểm chứng. Đây không phải chứng nhận bảo mật hay kết quả kiểm thử trên mọi môi trường.

### Đề xuất ưu tiên trước khi bàn giao

1. Sửa markup của ảnh dự án đầu tiên; chạy HTML validator và xử lý các lỗi được báo.
2. Đồng bộ tên dự án/người sở hữu ở tiêu đề trang, metadata tác giả và chân trang.
3. Thay `href="#"` bằng URL dự án thật hoặc bỏ liên kết nếu dự án chưa có trang đích.
4. Cập nhật các liên kết email, GitHub và mạng xã hội để nhãn, nội dung và URL cùng trỏ đúng đích.
5. Sửa cây thư mục trong README để phản ánh đúng vị trí `docs/RELEASENOTE.md`.
6. Tiếp tục kiểm tra điều hướng nội bộ, liên kết liên hệ và trải nghiệm trên trình duyệt/thiết bị thực tế; lưu lại kết quả.
7. Chạy thử các hướng dẫn Python và Docker nếu đây là phương thức triển khai bàn giao; lưu lại lệnh và kết quả.
8. Bổ sung log E2E và kiểm tra hiệu năng/quét bảo mật phù hợp với môi trường triển khai; ảnh responsive hiện đã có trong `docs/screenshots/`.

## 5. Kết quả kiểm thử bổ sung

| Nội dung | Kết quả |
|---|---|
| Rà soát tĩnh HTML/CSS/tài liệu | Đã thực hiện; phát hiện các vấn đề được liệt kê trong báo cáo. |
| Mở trang trong trình duyệt | Đã thực hiện với GitHub Pages và bản HTML cục bộ bằng Microsoft Edge; đã kiểm tra nội dung hiển thị ở ba kích thước viewport. |
| Chụp ảnh responsive | Đã thực hiện: 390 × 844, 768 × 1024 và 1440 × 1000; ảnh lưu trong `docs/screenshots/`. |
| Kiểm tra GitHub Pages | HTTP 200; đã xác nhận trang, CSS và ảnh đại diện tải được. SHA-256 của `index.html`, `assets/css/styles.css` và `assets/img/images.jpg` trên Pages trùng khớp với repository tại thời điểm kiểm tra. |
| Kiểm tra responsive trên Pages | Tại viewport 390 × 844, 768 × 1024 và 1440 × 1000: đủ 4 anchor section, liên kết điều hướng hiển thị, ảnh tải thành công; lưới lần lượt 1, 2 và 3 cột. |
| Kiểm thử Docker | Chưa thực hiện. |
| Đo hiệu năng | Chưa thực hiện. |
| Quét bảo mật tự động | Chưa thực hiện. |
| Kiểm tra định dạng Markdown | Đã rà soát nội dung và khoảng trắng cuối dòng; chưa chạy Markdown linter. |

## 6. Chấm điểm theo tiêu chí A2.2

Điểm dưới đây là đánh giá theo bằng chứng có trong repository và kiểm tra triển khai tại thời điểm lập báo cáo. Các tiêu chí về trình bày/demo chỉ có thể chấm tạm thời nếu chưa có video hoặc buổi demo được quan sát.

| Tiêu chí | Trọng số | Điểm | Nhận xét và căn cứ |
|---|---:|---:|---|
| A2.2.TC1 — Repository, commit và quá trình sửa lỗi | 20% | **15/20** | Có tối thiểu 3 commit chứa thay đổi có ý nghĩa: sửa ảnh responsive (`e1e7f7f`), release note (`24978b2`), README (`9adaee9`) và báo cáo (`8174c8a`). Có commit `fix(img): responsive image, closes #1` thể hiện sửa lỗi. Trừ điểm vì một số thông điệp chưa rõ/chưa chuẩn (`fix(feat): change`, `docs(note) : Add ...`) và lịch sử còn commit tự động của môi trường. |
| A2.2.TC2 — README và AI_LOG | 15% | **11/15** | README tiếng Việt trình bày dự án, yêu cầu, cấu hình, chạy trên Windows/macOS/Linux/Docker; tuy nhiên cây thư mục trong README chưa khớp vị trí hiện tại của release note. AI_LOG có ghi thay đổi lớn và nội dung cập nhật, nhưng hiện mới có một mục; chưa nêu rõ phần việc AI hỗ trợ, phần người học tự thực hiện/đối chiếu, nguồn tham khảo và xác nhận trách nhiệm học thuật. |
| A2.2.TC3 — GitHub Pages, tính nhất quán và minh chứng | 30% | **27/30** | URL [GitHub Pages](https://huy020608.github.io/My_cV/) trả HTTP 200. Đã kiểm tra trang tại ba viewport; bốn section điều hướng có đủ, ảnh tải thành công và lưới đổi 1/2/3 cột. SHA-256 của HTML, CSS và ảnh đại diện trực tuyến trùng repository. Trừ điểm vì một số liên kết dự án/liên hệ còn placeholder hoặc sai đích; chưa kiểm tra trên nhiều trình duyệt/thiết bị. |
| A2.2.TC4 — Release note v1.0 và luồng end-to-end | 20% | **15/20** | `docs/RELEASENOTE.md` ghi phiên bản v1.0.0, chức năng mới, lỗi sửa và giới hạn. Luồng triển khai đã kiểm chứng một phần bằng truy cập Pages và đối chiếu hash tài nguyên; ảnh viewport được lưu kèm. Trừ điểm vì release note chưa trỏ tới minh chứng/kịch bản E2E cụ thể, một số lỗi/giới hạn còn được ghi nhận và chưa có video/log kiểm thử phát hành. |
| A2.2.TC5 — Demo và giải thích quyết định kỹ thuật | 15% | **6/15** | README, release note và báo cáo cung cấp cơ sở để giải thích HTML/CSS tĩnh, responsive, Docker tùy chọn và giới hạn sản phẩm. Chưa có kịch bản, video hoặc buổi demo được quan sát; chưa có bằng chứng về phần trả lời câu hỏi nên điểm này chỉ là đánh giá tài liệu, không đại diện cho kỹ năng trình bày trực tiếp. |
| **Tổng điểm** | **100%** | **74/100** | **Đạt một phần; cần khắc phục các mục ưu tiên và bổ sung minh chứng demo trước khi bàn giao/chấm chính thức.** |

### Ưu tiên cải thiện để tăng điểm

1. Chuẩn hóa thông điệp commit rõ ràng, nhất quán; bảo đảm commit mô tả cụ thể lỗi, thay đổi và kết quả kiểm thử.
2. Bổ sung AI_LOG trung thực: phân biệt nội dung AI hỗ trợ với phần tự làm, cách kiểm chứng, nguồn tham khảo và trách nhiệm của người nộp bài; chỉ ghi việc đã thực hiện thật.
3. Hoàn thiện URL các dự án, email, GitHub và mạng xã hội; đồng bộ tên hiển thị trên trang với tên dự án.
4. Bổ sung vào release note kịch bản E2E có bước thực hiện, kết quả mong đợi/thực tế và liên kết ảnh/log liên quan.
5. Chuẩn bị demo ngắn: giới thiệu mục tiêu, điều hướng các section, minh họa responsive, giải thích HTML/CSS và các giới hạn; thử trước trên URL Pages đang hoạt động.
