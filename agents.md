# 🤖 Hướng dẫn AI Assistants & Quy tắc Component Bảo trì

> Chi tiết đầy đủ xem tại file [AGENTS.md](./AGENTS.md).

### 🛑 QUY TẮC CỐT LÕI (BẤT DI BẤT DỊCH)
1. **Component Bảo Trì Là Reusable:**
   - File chính: `src/components/maintenance/MaintenancePoster.astro`
   - File forwarder: `src/components/MaintenancePoster.astro`
   - **TUYỆT ĐỐI KHÔNG XÓA** component này, kể cả khi website đã mở lại bình thường.
2. **Cơ chế Bật / Tắt:**
   - Tại `src/pages/index.astro`: điều khiển bằng cờ `const isMaintenance = true;` / `false;`.
   - **Chỉ gỡ poster** khi Khoa Tran (@rio_vicorne) trực tiếp yêu cầu.
3. **Quy chuẩn Thiết kế:**
   - Nền Pure Dark `#080a0e`, card `#0f141c`.
   - Text Ghostwrite Shimmer (`.fx-shimmer`): chữ tĩnh mờ dịu `38%`, dải sáng quét qua làm rõ nét từng chữ (`#ffffff`).
   - Loading console neon đa sắc rực rỡ (cyan, purple, pink, amber, green).
   - Chỉ giữ duy nhất 2 kênh liên hệ: **TikTok** (`@rio_vicorne`) và **Email** (`khoatran.payment@gmail.com`).
