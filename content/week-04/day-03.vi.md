+++
title = "Ngày 03 - 07/10/2026 (Remote)"
weight = 3
+++

## Tích hợp Hệ thống, Kiểm thử E2E & Hoàn thành Nghiệm thu DEMO 1

Hôm nay nhóm tập trung tối đa nguồn lực để tích hợp liên phân hệ, rà soát tính toàn vẹn của Transaction và chạy thử nghiệm toàn bộ luồng nghiệp vụ đầu-cuối (E2E), chính thức nghiệm thu hoàn thành các mục tiêu của **DEMO 1**.

- **Tích hợp Toàn diện Frontend & Backend:**
  - Hoàn tất tích hợp toàn bộ giao diện Quản lý Nhà cung cấp (thêm, sửa, tìm kiếm, xem danh sách SKU phân phối) với API Backend.
  - Kết nối luồng Tạo phiếu nhập hàng (giao diện Supervisor) với module Nhà cung cấp: dropdown load danh sách đối tác thật, tự động lọc danh sách SKU theo nhà cung cấp được chọn.
  - Kết nối giao diện Receiver: hiển thị danh sách phiếu được giao trong hàng đợi công việc.

- **Review Chéo Transaction & Tính Toàn Vẹn Sổ Cái (`stock_ledger`):**
  - Cùng Nam Nguyen rà soát kỹ lưỡng DB Transaction tại endpoint Nhận hàng (`POST /api/receipts/{id}/receive`) và Duyệt điều chỉnh (`POST /api/adjustments/{id}/approve`):
    - **Đảm bảo tính Atomic:** Việc cập nhật `inventory` và ghi lịch sử `stock_ledger` thực thi trong cùng một Prisma transaction. Nếu ghi sổ cái thất bại, toàn bộ thao tác rollback, tồn kho không thay đổi.
    - **Chặn ghi đè:** Phiếu trạng thái `COMPLETED` sẽ lập tức bị từ chối nếu có request nhận hàng gửi tiếp.
    - **Ràng buộc Lô & Vị trí:** Bắt buộc nhập `lotNo` và `expiryDate` với sản phẩm có cờ `is_lot_tracked`; kiểm tra không vượt quá khối lượng tối đa của Bin Location.

- **Chạy Kiểm thử E2E & Nghiệm thu 2 Kịch bản Demo:**
  - **Kịch bản 1 (Nhập hàng & Cất hàng - Bắt buộc):**
    1. `SUPERVISOR` tạo phiếu nhập hàng (`RC-20261007-001`) với Nhà cung cấp NXB Kim Đồng, chọn SKU, số lượng 100, phân công cho `RECEIVER`.
    2. `RECEIVER` nhận việc, nhập số lượng thực nhận (100), số Lô, Ngày hết hạn, chọn Bin cất hàng (`BIN-A-01`).
    3. *Nghiệm thu:* Phiếu chuyển sang `COMPLETED`, tồn kho tại `BIN-A-01` tăng chính xác 100 đơn vị, sổ cái `stock_ledger` ghi nhận 1 dòng `RECEIPT` đầy đủ thông tin truy vết, bảng `sku_suppliers` tự động liên kết thành công.
  - **Kịch bản 2 (Kiểm kê & Điều chỉnh - Tự chọn):**
    1. `SUPERVISOR` tạo đợt kiểm kê tại `BIN-A-01` gán cho `INSPECTOR`.
    2. `INSPECTOR` kiểm đếm thực tế phát hiện tồn kho chỉ còn 98 (lệch -2). Bấm "Tạo đề xuất điều chỉnh" (`POST /api/adjustments`) với lý do hao hụt bảo quản.
    3. `WH_MANAGER` xem đề xuất và bấm **Duyệt (Approve)**.
    4. *Nghiệm thu:* Hệ thống gọi `InventoryLedgerService`, tồn kho giảm về 98, ghi nhận 1 bút toán `ADJUST_OUT` trên Sổ cái.

- **Kiểm thử Modal In Mã QR & Dữ liệu Seed Data:**
  - Kiểm tra Popup mã QR tại màn hình SKU/UOM: hiển thị QR code to rõ nét, đúng tỷ lệ quy đổi ra `base_uom`, nút "In tem nhãn" mở hộp thoại in trình duyệt chuẩn chỉnh.
  - Chuẩn bị bộ Seed Data sạch sẽ (Nhà cung cấp, SKUs nông sản có hạn sử dụng, Bin locations, và tài khoản theo từng Role).

- **Kết quả:** Nhóm hoàn thành xuất sắc toàn bộ yêu cầu của Demo 1 trước tiến độ, sẵn sàng chuyển trọng tâm sang chặng tiếp theo!
