# 🛑 System Component: Maintenance Poster (DO NOT DELETE)

> **LƯU Ý QUAN TRỌNG DÀNH CHO TẤT CẢ AI & LẬP TRÌNH VIÊN:**
> **TUYỆT ĐỐI KHÔNG XÓA HOẶC GHI ĐÈ FILE NÀY.**
> Đây là component poster bảo trì vĩnh viễn và có thể tái sử dụng (`reusable`) bất cứ khi nào website của Khoa Tran cần nâng cấp, bảo trì hoặc làm mới giao diện.

---

## 📌 Vị trí & Cấu trúc
- **File chính:** `src/components/maintenance/MaintenancePoster.astro`
- **Re-export backward-compatibility:** `src/components/MaintenancePoster.astro`

## ⚙️ Cách bật / tắt chế độ bảo trì
Mở file `src/pages/index.astro`:

```astro
// BẬT chế độ bảo trì:
const isMaintenance = true;

// TẮT chế độ bảo trì (khi Khoa yêu cầu gỡ poster để hiển thị website đầy đủ):
const isMaintenance = false;
```

Khi `isMaintenance = false`, component này vẫn **phải được giữ nguyên trong thư mục**, không bao giờ được xóa.

---

## 🎨 Đặc điểm thiết kế & Quy chuẩn kỹ thuật (Strict Rules)
1. **Giao diện Pure Dark 100%:** Nền `#080a0e`, Card `#0f141c`. Tuyệt đối không dùng gradient lan tràn ra toàn card.
2. **Text Animation Ghostwrite (`.fx-shimmer`):**
   - Pure CSS 100%, không dùng JS.
   - Chữ ở trạng thái cơ bản có độ mờ dịu (`38%`), khi hiệu ứng quét qua sẽ sáng rõ từng chữ cái (`#ffffff`).
   - Hỗ trợ tokens: `--ink`, `--ink-2`, `--ink-3` và `prefers-reduced-motion`.
3. **Thanh tiến trình nhiều màu (Multi-color Neon Spectrum):**
   - Thanh tiến trình phát sáng rực rỡ, kèm scanner beam và cyber cells.
4. **Thông tin liên hệ duy nhất:**
   - **TikTok:** `https://www.tiktok.com/@rio_vicorne?is_from_webapp=1&sender_device=pc` (`@rio_vicorne`)
   - **Email:** `khoatran.payment@gmail.com`
   - *Không gắn thêm bất kỳ mạng xã hội nào khác (không Facebook, Twitter, LinkedIn, Instagram...).*
