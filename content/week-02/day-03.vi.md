+++
title = "Ngày 03 - 23/09/2026 (Remote)"
weight = 3
+++

## Nhận nhiệm vụ Sprint 0 & Lên kế hoạch

Hôm nay nhóm bắt đầu bước vào **Sprint 0** với nhiệm vụ: Thiết kế nghiệp vụ và Database cho hệ thống Mini-WMS.

### 1. Thông tin chung

- **Thời gian:** 23/09/2026 – 28/09/2026 (4 ngày làm việc)
- **Mục tiêu:** Nhóm 5 thành viên tự chia 5 domain, thống nhất quy ước và nộp một bộ tài liệu thiết kế duy nhất (ERD, Business Flow, Data Dictionary, Business Rules).
- **Drive lưu trữ:** [Thư mục WMS_Sprint0](https://drive.google.com/drive/folders/1riQFgBk4ZDFgUm5EyZwi4B2pivqjxqOu?usp=sharing)

### 2. Kế hoạch ngày hôm nay (T4 23/09)

Nhóm đã họp và thực hiện các công việc sau theo đúng kế hoạch:

- Thống nhất các quy ước chung về thiết kế CSDL:
  - **Tên bảng:** `snake_case`, số nhiều tiếng Anh.
  - **Tên cột:** Khóa chính `id`, khóa ngoại `<bảng_số_ít>_id`.
  - **Kiểu dữ liệu:** Khóa chính `BIGINT`, tồn kho dùng `DECIMAL(18,4)`, thời gian dùng `TIMESTAMP`.
  - Bắt buộc có các cột audit (`created_at`, `updated_at`, v.v.) và cấm xóa cứng dữ liệu giao dịch.
- Phân chia 5 Domain cho các thành viên:
  - **A:** Authentication & RBAC
  - **B:** Warehouse Structure
  - **C:** Product & Supplier
  - **D:** Inventory Model
  - **E:** Stock Ledger & Movement
- Phác thảo luồng Business Flow chung (Inbound, Putaway, Pick, Ship...).
