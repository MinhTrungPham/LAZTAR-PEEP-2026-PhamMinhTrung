+++
title = "Day 02 - 06/10/2026 (Remote)"
weight = 2
+++

## Implementing the Complete Supplier Module & SKU-Supplier Mapping

Today was a remote working day. The team accelerated backend feature delivery to wrap up the entire Supplier module early, enabling immediate integration with the Inbound workflow and Demo 1 preparation.

- **Personal Task (Backend - Full Delivery of Supplier & Partner Management):**
  - **Module & Service Layer Architecture:** Built `SuppliersModule`, `SuppliersController`, and `SuppliersService` within the project's NestJS structure.
  - **DTOs & Strict Validation:** Defined `CreateSupplierDto`, `UpdateSupplierDto`, and `GetSuppliersQueryDto` utilizing `class-validator` (enforcing strict validation on supplier code, name, tax code, and contact).
  - **Delivered Complete Supplier CRUD:**
    - `POST /api/suppliers`: Created new suppliers with uniqueness checks on `code` (throwing `ConflictException` on duplicates), default `ACTIVE` status.
    - `GET /api/suppliers`: Paginated supplier list with search filtering on name/code and standard pagination metadata.
    - `GET /api/suppliers/{id}`: Detailed supplier view with `NotFoundException` handling.
    - `PUT /api/suppliers/{id}`: Updated partner information and toggled `ACTIVE`/`INACTIVE` status.
  - **Supplier SKUs Listing API (`GET /api/suppliers/{id}/skus`):**
    - Executed join queries across `sku_suppliers`, `skus`, and `uoms` tables.
    - Returned catalog items with `skuId`, `skuCode`, `skuName`, `supplierSkuCode`, `baseUomName`, and `isPreferred`.
  - **Cross-module Inbound Support:** Provided helper methods for Nam Nguyen's receipt workflow to validate suppliers and automatically persist `sku_suppliers` associations upon receiving new products.
  - **Unit Testing & API Documentation:** Wrote unit tests for service methods, exported Swagger UI and Postman collections for Vy Tran's frontend integration.

- **Team Coordination Progress:**
  - **Nam Nguyen:** Completed schema and receipt creation API `POST /api/receipts` (`NEW` / `ASSIGNED`), preparing transactions for the receive step.
  - **Thuan Le:** Finalized cycle count creation `POST /api/cycle-counts` and the barcode retrieval endpoint `GET /api/qrcodes/sku/{skuId}/uom/{uomId}`.
  - **Vy Tran:** Built the UI table for supplier management and began live API data binding.
