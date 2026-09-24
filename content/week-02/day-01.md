+++
title = "Day 01 - 21/09/2026 (On-site)"
weight = 1
+++

## Mini-WMS Project Study

Today we received the Mini-WMS project document (mock client: FreshLink Produce). Here is the summary of the core concepts for this agricultural warehouse management system:

### 1. End-to-End Operational Flow

The system follows a strict operational sequence:
**INBOUND** → **PUTAWAY** → **ALLOCATION** → **PICKING** → **PACKING** → **DELIVERY** → **(RETURN if any)**

### 2. Core Business Logic

The system must adhere to 8 real-world warehouse rules:

1. **Available vs Physical Stock**: Physical quantity differs from salable quantity since some items might be reserved for existing orders.
2. **UOM Conversion**: Must accurately convert units between ordering (e.g., boxes) and tracking (e.g., kilograms).
3. **FEFO (First Expired First Out)**: Prioritize dispatching items that expire earliest, not just the ones that came in first.
4. **Catch Weight**: Inventory deduction and billing are based on the actual weighed amounts (not theoretical ordered quantities).
5. **Shortage Handling**: Supports flexible resolutions for missing items: short shipping, item substitutions, or backordering.
6. **Adjustment Approvals**: Inventory modifications require strict managerial authorization to prevent fraud.
7. **Data Integrity**: Mechanisms to prevent duplicate opening stock imports.
8. **Concurrency**: Safely handle data conflicts when multiple users interact with the same bin location simultaneously.

### 3. Crucial System Principles

- **Stock Ledger**: The heart of the system. The stock history table is append-only. No UPDATE or DELETE is allowed. Mistakes are corrected via reversing entries (like accounting).
- **Single Source of Truth**: All inventory changes MUST route through a single service (`InventoryLedgerService`).

### 4. Tech Stack

- **Backend:** NestJS, PostgreSQL 16 + Prisma ORM
- **Frontend:** React + Next.js (Mobile-first design)
- **Infrastructure:** Docker Compose, GitHub Actions (CI)
