+++
title = "Ngày 01 - 21/09/2026 (On-site)"
weight = 1
+++

## Tìm hiểu dự án Mini-WMS

Hôm nay mình nhận tài liệu về dự án Mini-WMS (khách hàng giả định: FreshLink Produce) để bắt đầu tìm hiểu. Dưới đây là tóm tắt các điểm quan trọng nhất của hệ thống quản lý kho nông sản này:

### 1. Luồng vận hành chính (End-to-End Flow)

Hệ thống đi qua các bước tuần tự:
**NHẬN HÀNG** → **CẤT HÀNG** → **PHÂN BỔ TỒN** → **SOẠN HÀNG** → **ĐÓNG GÓI** → **GIAO HÀNG** → **(TRẢ HÀNG nếu có)**

### 2. Các nghiệp vụ cốt lõi (Core Business Rules)

Hệ thống phải tuân thủ 8 nguyên tắc kho bãi thực tế:

1. **Tồn khả dụng ≠ Tồn vật lý**: Hàng trong kho không đồng nghĩa với hàng có thể bán (do đã bị "giữ chỗ" cho đơn khác).
2. **Quy đổi Đơn vị tính (UOM)**: Luôn phải quy đổi chính xác từ đơn vị đặt hàng (thùng/hộp) sang đơn vị lưu kho (kg).
3. **Quy tắc xuất hàng FEFO**: Hàng tươi sống phải ưu tiên xuất lô hết hạn TRƯỚC (First Expired First Out), không dùng FIFO.
4. **Catch weight (Cân thực tế)**: Trừ tồn kho và tính tiền dựa trên số cân thực tế lúc giao, không theo số lượng lý thuyết lúc đặt.
5. **Xử lý thiếu hàng**: Cung cấp các tuỳ chọn linh hoạt khi kho thiếu hàng: giao thiếu, đổi hàng thay thế, hoặc hẹn giao bù.
6. **Kiểm duyệt điều chỉnh tồn**: Mọi thao tác sửa tồn kho bắt buộc phải có người phê duyệt (ngăn chặn gian lận).
7. **Bảo vệ toàn vẹn dữ liệu**: Cơ chế chống chạy trùng (nhập đúp dữ liệu tồn đầu kỳ).
8. **Đồng thời (Concurrency)**: Xử lý conflict an toàn khi có nhiều thao tác xuất/nhập diễn ra cùng lúc trên một vị trí kho.

### 3. Nguyên tắc hệ thống "Sống còn"

- **Sổ cái tồn kho (Stock Ledger)**: Đây là trái tim của hệ thống. Bảng ghi lịch sử tồn kho chỉ được thêm mới (append-only). Tuyệt đối không UPDATE/DELETE. Nếu sai, phải tạo bút toán đảo.
- **Một cửa duy nhất (Single Source of Truth)**: Mọi thay đổi tồn kho bắt buộc đi qua một service duy nhất là `InventoryLedgerService`.

### 4. Công nghệ sử dụng

- **Backend:** NestJS, PostgreSQL 16 + Prisma ORM
- **Frontend:** React + Next.js (Mobile-first)
- **Hạ tầng:** Docker Compose, GitHub Actions (CI)
