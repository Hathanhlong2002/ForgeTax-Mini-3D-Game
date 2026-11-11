FORGETAX MINI 3D GAME — SOURCE HOÀN THIỆN (bản 2026-11-11, cập nhật mới nhất)
============================================================

CẬP NHẬT TRONG BẢN NÀY (so với gói 01:42)
- Sửa lỗi nạp model Lv.90 "Failed to parse URL from assets/models/lv90.glb":
  mọi URL tài sản (model/poster/linh thú) được dựng từ địa chỉ tuyệt đối
  và lệnh nạp model được bọc chắn lỗi.
- Ảnh Bộ sưu tập: thẻ Lv.90–100 dùng poster (kiếm + hiệu ứng + linh thú),
  ảnh Lv.11–89 render kèm VFX đúng tier của level.
- Sửa nút Thành tích bị cắt khỏi màn hình điện thoại.

CÁCH CHẠY
- Giải nén, rồi chạy một web server tĩnh trong thư mục này, ví dụ:
    python3 -m http.server 8000
  sau đó mở http://localhost:8000/index.html
- KHÔNG mở thẳng file index.html bằng file:// vì trình duyệt sẽ chặn
  việc nạp model 3D (CORS). Chạy qua server tĩnh là chơi đầy đủ.

CẤU TRÚC GÓI
- index.html ......... toàn bộ game (giao diện + logic + thư viện 3D
                       đã nhúng; model Lv.1–89 nhúng sẵn trong trang)
- assets/models/ ..... 11 model Thrixel endgame Lv.90–100 (lv90.glb … lv100.glb)
                       + smoke-dragon-head.glb (Rồng Khói — hiện ở hang khi đạt Lv.100)
- assets/cutscenes/ .. ForgeTax-Teaser-10s.mp4 (hé màn 10s khi rèn Lv.90, cắt 38–48s)
                       ForgeTax-Cutscene-60s-TrieuHoiLinhThu.mp4 (tri ân ~60s khi rèn Lv.100)
- assets/posters/ .... 11 poster linh thú Lv.90–100 (lv90.jpg … lv100.jpg)
- assets/spirits/ .... 11 ảnh linh thú nền đen Lv.90–100 (lv90.webp … lv100.webp)

NỘI DUNG BẢN NÀY
- 100 level kiếm, mỗi level một model riêng; Lv.90–100 là model Thrixel.
- VFX động 7 tier cho Lv.11–100 theo nguyên tố; linh thú hiện sau kiếm ở Lv.90–100.
- Độ khó vỡ đã cân bằng Monte Carlo (Lv.10 ≈ 95,5% · Lv.60 ≈ 32,9% · Lv.100 ≈ 4,2%).
- Sự kiện Rồng Khói phá lò khi trễ cống + sửa lò; gói cải thiện: juice/số bay,
  Đại Thành Công ×2, 15 thành tích mở 15 relic vĩnh viễn (localStorage),
  nhiệm vụ theo vòng, sự kiện ngẫu nhiên, tổng kết vòng + kỷ lục, onboarding ván đầu.

GHI CHÚ KỸ THUẬT
- 11 model trong assets/models là file Thrixel GỐC (texture chưa nén lại)
  nên nặng hơn bản đang chạy trên Muse (bản đó dùng bản đã tối ưu
  374KB–1,06MB/cây). Hình học và chất liệu giống hệt; chỉ khác dung lượng
  và tốc độ nạp lần đầu ở Lv.90+.
- Poster .jpg được chuyển từ poster .png gốc; ảnh spirits là file webp gốc.
- Tiến trình lưu (thành tích, kỷ lục, relic đã mở) nằm trong localStorage
  của trình duyệt nơi chơi.
