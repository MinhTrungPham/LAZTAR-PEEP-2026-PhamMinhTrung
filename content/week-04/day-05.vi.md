+++
title = "Ngày 05 - 09/10/2026 (Remote)"
weight = 5
+++

## Triển khai Phân hệ Bút toán đảo & Điều chỉnh nhanh theo Plan Mới

- **Nhiệm vụ cá nhân (Backend - Bút toán đảo & Điều chỉnh nhanh):**

  - **Phân hệ Bút toán đảo (`ReversalsModule`):**

    - Cấu trúc bảng `ledger_reversal_requests`: lưu `originalLedgerId`, `reason`, `requestedBy`, `status` (`PENDING`), `reviewedBy`, `reviewNote`.
    - Viết DTOs với validation: `CreateReversalRequestDto`, `UpdateReversalRequestDto`, `ApproveReversalRequestDto`, `RejectReversalRequestDto`.
    - **Hiện thực API Tạo yêu cầu đảo (`POST /api/reversals/requests`):**
      - Truy vấn dòng sổ cái gốc trong `stock_ledger` theo `originalLedgerId`.
      - **Kiểm tra an toàn 1 (Chỉ đảo chứng từ 1 vế):** Nghiêm cấm đảo các chứng từ nhiều vế phức tạp (Pick, Putaway, Transfer). Chỉ cho phép đảo các bút toán độc lập (như điều chỉnh kiểm kê nhầm `ADJUST_IN`/`ADJUST_OUT`).
      - **Kiểm tra an toàn 2 (Không có movement đè lên):** Kiểm tra lịch sử giao dịch của tồn kho tương ứng, nếu đã có phát sinh movement sau thời điểm đó thì từ chối yêu cầu để tránh sai lệch lũy kế.
    - **Hiện thực API Cập nhật (`PUT /api/reversals/requests/{id}`):** Chỉ cho phép chỉnh sửa `reason` khi yêu cầu còn ở trạng thái `PENDING` và người sửa chính là `requestedBy`.
    - **Hiện thực API Admin Duyệt (`POST /api/reversals/requests/{id}/approve`):**
      - Sử dụng Prisma `$transaction`: Đổi status thành `APPROVED`, insert 1 dòng mới vào `stock_ledger` loại `REVERSAL` với `qtyChange` ngược dấu và `reversalOfId` trỏ về dòng gốc (giữ nguyên tắc append-only, không xóa/sửa dòng cũ), đồng thời hoàn trả số lượng trong `inventory`.
    - **Hiện thực API Admin Từ chối (`POST /api/reversals/requests/{id}/reject`):** Cập nhật `status = REJECTED` và lưu `reviewNote`.
  - **Phân hệ Điều chỉnh nhanh (Quick Adjustment):**

    - **Tạo Draft (`POST /api/adjustments`):** Tạo phiếu ở trạng thái `DRAFT`, lưu `proposedBy` và snapshot `inventoryVersion` từ bảng `inventory` nhằm chuẩn bị cơ chế chống xung đột concurrency.
    - **Gửi duyệt (`POST /api/adjustments/{id}/submit`):** Đổi status sang `PENDING_APPROVAL`.
    - **Duyệt (`POST /api/adjustments/{id}/approve`):** Bắt buộc chạy Transaction kiểm tra: người duyệt phải khác người đề xuất (`approvedBy != proposedBy`), kiểm tra `inventoryVersion` (nếu có giao dịch khác làm đổi version sẽ ném lỗi `409 Conflict`), cập nhật tồn kho và ghi sổ cái `ADJUST_IN` hoặc `ADJUST_OUT`.
- **Tổng kết tuần 4:**

  - Khép lại tuần 4 trọn vẹn: Đã hoàn thành nghiệm thu Demo 1 và khởi động xuất sắc các module cốt lõi của chặng cuối Demo 2.
  - Sẵn sàng bước sang tuần kế tiếp để hoàn thiện luồng STAGING, TRANSIT và kiểm thử toàn diện hệ thống!
