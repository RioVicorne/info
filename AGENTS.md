# 🤖 AGENTS.MD — HƯỚNG DẪN DÀNH CHO CÁC AI ASSISTANTS

> **Dự án:** Portfolio cá nhân của **Khoa Tran (@rio_vicorne)**  
> **Framework:** Astro (Static Site Generation)  
> **Deployment:** Cloudflare Pages (Project `info` · `https://info-4ab.pages.dev` / `https://info.khoa.engineer`)  
> **Repository:** `https://github.com/RioVicorne/info.git` (Branch `main`)

Tất cả các AI Assistant (Cursor AI, Antigravity, Claude Code, GitHub Copilot, Roo...) khi làm việc trên codebase này **BẮT BUỘC** phải tuân theo các nguyên tắc được định nghĩa dưới đây.

---

## 🛑 NGUYÊN TẮC BẤT DI BẤT DỊCH (CRITICAL IMMUTABLE RULES)

### 1. TUYỆT ĐỐI KHÔNG XÓA COMPONENT BẢO TRÌ (`MaintenancePoster.astro`)
- **Vị trí lưu trữ chính:** `src/components/maintenance/MaintenancePoster.astro`
- **File chuyển tiếp tương thích:** `src/components/MaintenancePoster.astro`
- **Tài liệu cảnh báo:** `src/components/maintenance/README.md`
- **Mục đích:** Đây là component poster bảo trì **vĩnh viễn và có thể tái sử dụng (`reusable`)** bất cứ khi nào Khoa Tran cần tạm dừng website để code tính năng mới, sửa lỗi hoặc redesign.
- **Quy tắc:**
  - **KHÔNG ĐƯỢC XÓA** file này trong bất kỳ hoàn cảnh nào.
  - Ngay cả khi website đã hoàn thiện và quay về chế độ hiển thị bình thường (`isMaintenance = false`), component này **phải được giữ nguyên** trong thư mục `src/components/maintenance/`.

### 2. CƠ CHẾ BẬT / TẮT CHẾ ĐỘ BẢO TRÌ (TOGGLE SWITCH)
Tại file `src/pages/index.astro`:
```astro
// Khi đang làm việc hoặc bảo trì:
const isMaintenance = true;

// Khi Khoa Tran yêu cầu gỡ poster để hiển thị website đầy đủ:
const isMaintenance = false;
```
- Khi `isMaintenance = true`: Astro render `<MaintenancePoster />` với giao diện full-bleed nền tối `#080a0e`.
- Khi `isMaintenance = false`: Astro render đầy đủ các section (`Header`, `ProfileHero`, `NowPlaying`, `About`, `PhotoGallery`, `Hobbies`, `Connect`, `Footer`).
- **Chỉ chuyển sang `false` khi Khoa Tran trực tiếp yêu cầu: "gỡ poster", "hãy gỡ poster đi", "xong rồi mở web lại".**

---

## 🎨 QUY CHUẨN THIẾT KẾ CỦA POSTER BẢO TRÌ

1. **Chuẩn Dark Theme & Solid Colors:**
   - Nền trang: `#080a0e` (Solid Dark, full bleed, không hở viền trắng/kem).
   - Khung poster (card): `#0f141c` với viền `#1e2638`. Tuyệt đối không dùng gradient lan tràn làm mất độ tương phản.
2. **Hiệu ứng chữ Ghostwrite AI Shimmer (`.fx-shimmer`):**
   - Áp dụng cho tiêu đề: `<div class="fx-shimmer">Website Đang Được Bảo Trì</div>`.
   - **Pure CSS 100%** (không dùng JavaScript).
   - Màu chữ nền ở trạng thái tĩnh: mờ dịu, dễ đọc (`38% opacity`).
   - Dải quang phổ chạy qua trong `2.8s`: làm sáng bừng, rõ nét từng chữ cái lên màu trắng tinh khôi (`#ffffff`).
   - Tuân thủ token: `--ink: #ffffff`, `--ink-2: #FF4FD8`, `--ink-3: #4FF8FF` và hỗ trợ `@media (prefers-reduced-motion: reduce)`.
3. **Thanh tiến trình nhiều màu sắc (High-Energy Neon Spectrum):**
   - Gradient đa sắc: Cyan, Blue, Purple, Pink, Orange, Amber, Lime, Green.
   - Hiệu ứng quét scanner và cyber cells phân đoạn.
4. **Kênh liên hệ DUY NHẤT (Chỉ giữ TikTok & Email):**
   - **TikTok:** `https://www.tiktok.com/@rio_vicorne?is_from_webapp=1&sender_device=pc` (`@rio_vicorne`)
   - **Email:** `khoatran.payment@gmail.com`
   - **CẤM:** Không thêm Facebook, Twitter/X, Instagram, LinkedIn, Discord hay bất kỳ mạng xã hội nào khác vào poster bảo trì.

---

## 📁 CẤU TRÚC THƯ MỤC DỰ ÁN (PROJECT DIRECTORY STRUCTURE)

```
Portfolio/
├── AGENTS.md                               # <-- File quy tắc tối cao cho AI
├── agents.md                               # <-- Alias / tham chiếu nhanh
├── README.md
├── package.json
├── astro.config.mjs
├── public/
│   ├── favicon.svg
│   └── images/                             # Ảnh cá nhân, ảnh chụp đường phố Sài Gòn
├── src/
│   ├── components/
│   │   ├── maintenance/                    # 🛡️ THƯ MỤC HỆ THỐNG BẢO TRÌ (BẤT TỬ)
│   │   │   ├── MaintenancePoster.astro    # Component chính thức (KHÔNG ĐƯỢC XÓA)
│   │   │   └── README.md                   # Cảnh báo và hướng dẫn sử dụng
│   │   ├── MaintenancePoster.astro         # Forwarder tương thích ngược
│   │   ├── Header.astro                    # Header thanh điều hướng
│   │   ├── ProfileHero.astro               # Hero giới thiệu bản thân
│   │   ├── NowPlaying.astro                # Trạng thái nghe nhạc Spotify / lofi
│   │   ├── About.astro                     # Giới thiệu tiểu sử ngắn
│   │   ├── PhotoGallery.astro              # Bộ sưu tập ảnh đường phố Sài Gòn
│   │   ├── Hobbies.astro                   # Sở thích cá nhân
│   │   ├── Connect.astro                   # Kênh kết nối & liên hệ
│   │   ├── Footer.astro                    # Chân trang
│   │   └── Toast.astro                     # Notification toast khi copy email
│   ├── layouts/
│   │   └── Layout.astro                    # Base HTML layout, Dark Mode & SEO
│   ├── pages/
│   │   └── index.astro                     # Trang chủ & cờ isMaintenance
│   └── styles/
│       └── global.css                      # CSS tokens và styles toàn cục
```

---

## 🚀 QUY TRÌNH BUILD & DEPLOY
Mỗi khi có thay đổi được Khoa Tran phê duyệt:
1. **Kiểm tra code & Build:**
   ```bash
   npm run build
   ```
2. **Deploy lên Cloudflare Pages:**
   ```bash
   npx wrangler pages deploy dist --project-name info --branch main
   ```
3. **Commit & Push lên Git:**
   ```bash
   git add .
   git commit -m "feat/fix: <mô tả thay đổi>"
   git push origin main
   ```
