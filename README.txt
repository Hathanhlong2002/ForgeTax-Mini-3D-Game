FORGETAX MINI 3D GAME — SOURCE (build 2026-11-12)
============================================================

CẬP NHẬT GẦN ĐÂY
- Kinh tế: lên cấp ×1.25 giá kiếm (trần 1000 tỷ @ Lv.100).
- Bảng 3D trên đe: đồng bộ level/model, Hi-DPI, vẽ có cache (giảm lag gõ).
- Sửa crash gõ búa: biến `celebratedLv` không đè hàm `upLv()`.
- Lv.90: clip 10s; Lv.100: phim tri ân 60s + model Rồng Khói.
- Perf: HUD nhiệt nhẹ, ít particle trên mobile/low-end.

CÁCH CHẠY (dev)
    python3 -m http.server 8000
  → http://localhost:8000/index.html
  Không mở file:// — CORS chặn model/cutscene.

BUILD / ĐÓNG GÓI
    ./scripts/optimize-media.sh   # tùy chọn: nén MP4/GLB, vẫn cùng tên file
    ./scripts/build-dist.sh
  → dist/ForgeTax-Mini-3D-itch.zip (index.html + README + assets/)
  Chi tiết: docs/OPTIMIZE-PLAN.md

CẤU TRÚC GÓI
- index.html ......... game + Three.js nhúng; model Lv.1–89 embed trong trang
- assets/models/ ..... lv90–100.glb, smoke-dragon-head.glb
- assets/cutscenes/ .. ForgeTax-Teaser-10s.mp4, ForgeTax-Cutscene-60s-…mp4
- assets/posters/ .... lv90–100.jpg
- assets/spirits/ .... lv90–100.webp
- assets/ui/ ......... icon, khung menu, nút

GHI CHÚ
- Cutscene + rồng GLB ~80MB — zip release nặng; cần HTTP server khi chơi.
- Save: localStorage (thành tích, relic, ngôn ngữ).
