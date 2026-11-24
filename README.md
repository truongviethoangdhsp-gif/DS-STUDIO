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


## V30 – Tối ưu mã nguồn
- Dung lượng `index.html` giảm từ ~12,7 MB xuống ~0,77 MB: bỏ ảnh nhúng trùng (thumbnail), đổi 4 ảnh PNG sang WebP (chất lượng 92).
- Thumbnail thư viện được tạo lúc chạy từ chính ảnh nền/wave.
- Chỉ nạp mẫu nền/wave đầu tiên trước, trang hiển thị ngay; các mẫu còn lại nạp nền.
- Cache lớp nền + wave: kéo thả chữ/logo không còn vẽ lại ảnh 1920×1080 mỗi khung hình.
- Cache đo chữ (xóa khi font tải xong); gộp logic logo trường/logo đối tác; gộp CSS trùng lặp, bỏ CSS/JS không dùng.
- Logo đối tác dùng `URL.createObjectURL` thay cho Base64, ảnh quá lớn được thu nhỏ về tối đa 1024px.
- Sửa lỗi: logo đối tác không còn bị bóp méo tỉ lệ; khung chọn logo trường không hiện khi kéo đối tượng khác; thứ tự ưu tiên chọn khớp thứ tự lớp vẽ.


## V31 – Viền chữ (stroke)
- Mỗi trường chữ (và chữ bổ sung) có tùy chọn "Viền chữ": bật/tắt, màu viền, độ dày (1–30, tính theo khung 1920px nên giữ tỉ lệ khi đổi kích thước).
- Tiêu đề mặc định vẫn viền trắng như trước; các trường khác mặc định tắt.


## Bản final đã tích hợp sửa lỗi tự xuống dòng
- Tích hợp trực tiếp vào mã nguồn final do người dùng cung cấp, không thay bằng nhánh V31 trước đó.
- Tất cả trường chữ mặc định đều tự ngắt dòng khi vượt quá 88% chiều rộng banner, bao gồm TIÊU ĐỀ và NGÀY THÁNG.
- Giữ các xuống dòng thủ công; hỗ trợ cả chuỗi dài không có dấu cách.
- Các chức năng, giao diện, tài nguyên nhúng và thiết lập hiện có của bản final được giữ nguyên.
\n\n## Bổ sung định dạng chữ hoa/thường\n- Thêm hai nút IN HOA và in thường ngay dưới ô nhập nội dung của từng trường chữ trong bảng định dạng.\n- Chuyển đổi trực tiếp nội dung đang nhập, hỗ trợ tiếng Việt; các định dạng và vị trí chữ được giữ nguyên.\n

## Xuất PowerPoint (.pptx)
- Thêm nút "Xuất PowerPoint" cạnh nút Xuất PNG; tạo file `ufls-banner.pptx` gồm 1 slide có cùng kích thước với banner đang chọn (1920 px = 13,33 in).
- Nền, wave, logo trường và logo đối tác là ảnh; tên trường, tiêu đề, nội dung, ngày tháng và chữ bổ sung là hộp chữ có thể sửa trực tiếp trong PowerPoint (giữ font, cỡ, màu, đậm/nghiêng/gạch chân, căn lề, giãn dòng, viền chữ).
- Thư viện PptxGenJS 4.0.1 được nhúng sẵn trong `index.html` (chỉ chạy khi bấm xuất), không cần Internet; file tăng thêm ~0,45 MB.
- Máy mở file cần cài các font Be Vietnam Pro, Montserrat, Oswald, Roboto; nếu thiếu, PowerPoint sẽ tự thay font khác.


## Cỡ chữ trường Nội dung
- Thanh kéo cỡ chữ của trường NỘI DUNG tăng giới hạn tối đa từ 75 lên 100 (mặc định vẫn 68).


## Bảng định dạng thu gọn
- Khi mở trang, 4 mục TÊN TRƯỜNG / TIÊU ĐỀ / NỘI DUNG / NGÀY THÁNG NĂM đều thu gọn; bấm vào tên mục để mở bảng chỉnh.


## Thêm mẫu nền và wave
- Thư viện nay có 4 nền (thêm "Nền bản đồ thế giới") và 4 wave (thêm "Wave đỏ – xanh 4"), nhúng trực tiếp dạng WebP trong `index.html`.
- Wave mới đã cắt bỏ phần trong suốt phía trên để nhẹ hơn; hiển thị không đổi (vẫn rộng bằng khung, bám đáy).


## Thêm nền thứ 5
- Thêm "Nền khuôn viên trường" (WebP nhúng sẵn); thư viện nay có 5 nền và 4 wave.


## Nút "Xuất file" gộp
- Các nút xuất gộp thành 1 nút **Xuất file ▾** ở góc trên phải; bấm để chọn PNG, JPEG, PDF hoặc PowerPoint (.pptx).
- JPEG: chất lượng 95%, nền lót trắng. PDF: 1 trang, kích thước theo banner (1920×1080 → 20 × 11,25 in), nội dung là ảnh (không sửa chữ được); tạo bằng mã tự viết, không cần thư viện.
- Bấm ra ngoài hoặc nhấn Esc để đóng menu.


## Footer gọn hơn
- Footer thu nhỏ: chữ 12px (11px trên điện thoại), padding và khoảng cách dòng giảm, hiển thị đúng 2 dòng (Designed & Developed by ZrVietHoang / © 2026 – All Rights Reserved).


## Hiển thị mặc định như zoom 67%
- Trên màn hình máy tính (rộng trên 1100px), giao diện tự thu nhỏ còn 67% (CSS `zoom`), để mở trang là thấy gọn như khi trình duyệt zoom 67%. Điện thoại/máy tính bảng không bị thu nhỏ.
- Muốn đổi mức thu nhỏ, sửa `--z:.67` trong khối `@media (min-width:1101px)` cuối phần CSS (ví dụ `.8` cho 80%).
- Đã thử kéo thả chữ trên bản đã thu nhỏ: toạ độ vẫn khớp.


## Footer luôn hiện
- Trên máy tính, trang vừa khít 1 màn hình: header ở trên, footer ở dưới cùng luôn thấy, không cần kéo xuống. Cột thư viện bên trái, bảng định dạng bên phải và vùng thiết kế tự cuộn bên trong khi nội dung dài.
- Điện thoại/máy tính bảng giữ cách hiển thị cuộn cả trang như trước.


## PDF nét hơn
- PDF được vẽ lại ở độ phân giải gấp 2 (1920×1080 → ảnh 3840×2160, JPEG chất lượng 96%) trên canvas ẩn, rồi nhúng vào trang PDF; kích thước trang không đổi (20 × 11,25 in). Chữ, viền chữ, logo và nền sắc nét hơn khi phóng to hoặc in; file PDF khoảng 1 MB.
- PNG và JPEG vẫn xuất đúng kích thước banner (1×).
