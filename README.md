# UFLS Design Studio

Công cụ thiết kế banner/phông nền UFLS chạy hoàn toàn trên trình duyệt (HTML + Canvas, không cần build).

## Chạy thử
Mở `index.html` bằng Chrome/Edge/Firefox. Google Fonts cần Internet; không có mạng sẽ dùng font dự phòng.

## Đưa lên GitHub Pages
Chỉ cần upload `index.html` (và `README.md`) → Settings → Pages → Deploy from a branch → `main` → `/ (root)`.
Các ảnh nền, wave, logo đã được nhúng sẵn (WebP) nên **không cần thư mục `assets/`**.

## Tính năng
- Thư viện nền/wave, thêm nhiều ảnh bằng nút tải; bật/tắt từng lớp.
- 4 trường chữ: tên trường, tiêu đề, nội dung, ngày tháng. Mỗi trường: font, cỡ, màu, đậm/nghiêng/gạch chân, căn lề, giãn dòng.
- Kéo thả chữ và logo, đường căn giữa tự hút; logo đổi kích thước bằng ô vuông góc dưới phải.
- Xuất PNG theo 4 kích thước. Chưa có xuất PDF.

## Bản tích hợp
- Sử dụng `index.html` do người dùng cung cấp làm mã nguồn chính.
- Footer đã được chuẩn hóa theo mẫu: nền navy `#232262`, chữ trắng, hai dòng căn giữa, bo góc và tự co giãn trên thiết bị di động.
- Toàn bộ nền, wave và logo được nhúng trực tiếp trong HTML; không cần thư mục `assets/`.


## V19 – Bố cục mặc định khi mở
- Tên trường mặc định thành hai dòng, căn giữa ở phần đầu banner.
- Logo UFLS được đặt bên trái cụm tên trường, theo đúng vị trí tham chiếu.
- Tiêu đề và nội dung mặc định hiển thị chữ mẫu “TEXT” để người dùng thay nhanh.
- Dòng ngày tháng dùng mẫu “Đà Nẵng, ngày 00 tháng 00 năm 2026”.
- Các trường vẫn kéo thả và chỉnh sửa độc lập như trước.


## V20 – Thư viện nền và wave cố định
- Bỏ chức năng tải ảnh nền/wave tùy ý từ giao diện.
- Thư viện có 3 nền: nền gốc, NEN 2 và NEN 3.
- Thư viện có 3 wave: wave gốc, wave 2 và wave 3.
- Ảnh bổ sung được lưu riêng trong `assets/background/` và `assets/wave/`, giữ nguyên PNG gốc.
- Có thể chọn mẫu bằng thumbnail; vẫn giữ chức năng bật/tắt lớp nền và wave.


## V22 – Bố cục mở mặc định theo ảnh tham chiếu
- Logo UFLS đặt bên trái cụm tên trường, tọa độ x=30%, y=4%, kích thước tương đối 4%.
- Tên trường hiển thị hai dòng, căn giữa theo trục ngang của banner, dùng màu navy và font Be Vietnam Pro đậm.
- Tiêu đề, nội dung và ngày tháng giữ bố cục mẫu đã thiết lập ở V19–V21.
- Nút Đặt lại khôi phục đúng bố cục mặc định này.


## V23 – Tinh chỉnh cụm logo và tên trường
- Font mặc định của tên trường đổi sang Montserrat.
- Logo UFLS đặt tại x=28.8%, y=3.5%, giữ kích thước 4%, nằm bên trái cụm tên trường như ảnh tham chiếu.
- Các vị trí mặc định khác được giữ nguyên.


## V24 – Xuất bố cục JSON
- Thêm nút “Xuất bố cục JSON” cạnh nút xuất PNG.
- File `ufls-layout.json` lưu kích thước canvas, trạng thái hiển thị các lớp, tọa độ/kích thước logo, toàn bộ nội dung và định dạng của 4 trường chữ, cùng lựa chọn nền/wave.
- Sau khi kéo thả và định dạng xong, nhấn nút này rồi gửi file JSON để tích hợp thành bố cục mặc định.
- File JSON không chứa ảnh nền/logo; các tài nguyên vẫn được quản lý riêng trong thư mục assets và HTML.


## V26 – Bố cục mặc định theo file JSON người dùng gửi
- Đã áp dụng chính xác tọa độ logo và các trường chữ từ `ufls-layout.json`.
- Tên trường: Montserrat 34px, đậm, căn giữa, hai dòng.
- Tiêu đề: Oswald 104px, đỏ, đậm, căn giữa.
- Nội dung: Oswald 68px, navy, đậm, căn giữa, giãn dòng 160%.
- Ngày tháng: Be Vietnam Pro 36px, navy, đậm/nghiêng, căn giữa.
- Logo: x=0.2856176004, y=0.0417764606, scale=0.0485098152.
- Kích thước banner 1920×1080; nền, wave và logo đều bật; mẫu nền/wave đầu tiên.


V26: Đã bỏ nút xuất bố cục JSON khỏi giao diện và giảm độ tương phản footer Designed & Developed by để hiển thị kín đáo hơn.


V27: Nhúng trực tiếp 4 mẫu nền/wave bổ sung vào index.html để tránh lỗi đường dẫn assets khi triển khai trên Vercel. Thư viện vẫn có 3 nền và 3 wave.


## V28 – triển khai một tệp
Toàn bộ ảnh nền, wave và logo đã được nhúng trực tiếp trong `index.html` dưới dạng dữ liệu Base64.
Khi đưa lên GitHub/Vercel, chỉ cần tải lên `index.html` (README không bắt buộc). Không cần thư mục `assets`.


## V29 – logo đối tác và chữ bổ sung
- Tải lên nhiều logo đối tác trực tiếp trong giao diện; logo được nhúng vào bộ nhớ trình duyệt khi tải và xuất cùng PNG.
- Kéo thả, thay đổi kích thước, nhân đôi hoặc xóa từng logo.
- Thêm nhiều đối tượng chữ độc lập; chỉnh nội dung, font, cỡ chữ, màu, căn lề, đậm/nghiêng; kéo thả, nhân đôi hoặc xóa.
- Các đối tượng bổ sung không thay đổi logo trường và bốn trường chữ mặc định.
- Chỉ cần triển khai `index.html`; toàn bộ tài nguyên gốc vẫn nhúng trong tệp.
