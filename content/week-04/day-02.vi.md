+++
title = "Ngày 02 - 06/10/2026 (Remote)"
weight = 2
+++

## Hiện thực trọn bộ Module Nhà cung cấp & Liên kết SKU-Supplier

Hôm nay là ngày làm việc từ xa (Remote). Nhóm đẩy nhanh tốc độ triển khai kỹ thuật nhằm hoàn thành sớm các chức năng Backend của phân hệ Nhà cung cấp, tạo nền tảng để kết nối ngay vào luồng Nhập hàng và chuẩn bị cho đợt Demo 1.

- **Nhiệm vụ cá nhân (Backend - Hoàn thiện toàn bộ Module Nhà cung cấp & Đối tác):**
  - **Khởi tạo & Cấu trúc Service Layer:** Xây dựng `SuppliersModule`, `SuppliersController`, và `SuppliersService` trong NestJS.
  - **Xây dựng DTOs & Validation:** Định nghĩa `CreateSupplierDto`, `UpdateSupplierDto`, và `GetSuppliersQueryDto` với `class-validator` (kiểm tra chặt chẽ mã NCC `code`, tên, mã số thuế `taxCode`, thông tin liên hệ `contact`).
  - **Hoàn thành trọn bộ CRUD Nhà cung cấp:**
    - `POST /api/suppliers`: Tạo mới nhà cung cấp, kiểm tra tính duy nhất của mã `code` (ném `ConflictException` nếu trùng), lưu trạng thái mặc định `ACTIVE`.
    - `GET /api/suppliers`: Lấy danh sách nhà cung cấp có phân trang chuẩn (`page`, `limit`), hỗ trợ tìm kiếm không phân biệt hoa thường theo `name` hoặc `code`.
    - `GET /api/suppliers/{id}`: Xem chi tiết thông tin nhà cung cấp (ném `NotFoundException` nếu không tồn tại).
    - `PUT /api/suppliers/{id}`: Cập nhật thông tin, thay đổi trạng thái hoạt động (`ACTIVE`/`INACTIVE`).
  - **API Quản lý mã SKU của Nhà cung cấp (`GET /api/suppliers/{id}/skus`):**
    - Thực hiện join giữa bảng `sku_suppliers` với `skus` và `uoms`.
    - Trả về danh sách SKU đối tác cung cấp kèm: `skuId`, `skuCode`, `skuName`, `supplierSkuCode`, `baseUomName`, và cờ `isPreferred`.
  - **Hỗ trợ liên phân hệ Inbound:** Cung cấp hàm helper cho service Nhập hàng của Nam Nguyen để tra cứu nhà cung cấp hợp lệ và tự động sinh bản ghi `sku_suppliers` khi nhập mã hàng mới.
  - **Tài liệu & Unit Test:** Viết unit test cho các service methods và xuất bộ Postman Collection / Swagger UI gửi cho Vy Tran tích hợp vào Frontend.

- **Tiến độ phối hợp cùng nhóm:**
  - **Nam Nguyen:** Xây dựng xong schema và API tạo phiếu nhập `POST /api/receipts` (`NEW` / `ASSIGNED`), bắt đầu xử lý transaction cho bước nhận hàng.
  - **Thuan Le:** Hoàn thành API tạo phiên kiểm kê `POST /api/cycle-counts` và endpoint trích xuất mã Barcode hàng hóa `GET /api/qrcodes/sku/{skuId}/uom/{uomId}`.
  - **Vy Tran:** Hoàn tất khung giao diện quản lý nhà cung cấp và bắt đầu binding dữ liệu thực tế từ API.
