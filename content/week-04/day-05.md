+++
title = "Day 05 - 09/10/2026 (Remote)"
weight = 5
+++

## Implementing Ledger Reversals & Quick Adjustments Under the New Plan

- **Personal Task (Backend - Ledger Reversals & Quick Adjustments):**

  - **Ledger Reversals Module (`ReversalsModule`):**

    - Modeled Prisma schema for `ledger_reversal_requests`: capturing `originalLedgerId`, `reason`, `requestedBy`, `status` (`PENDING`), `reviewedBy`, and `reviewNote`.
    - Defined validation DTOs: `CreateReversalRequestDto`, `UpdateReversalRequestDto`, `ApproveReversalRequestDto`, and `RejectReversalRequestDto`.
    - **Implemented Create Reversal Request API (`POST /api/reversals/requests`):**
      - Queried the target ledger entry from `stock_ledger` via `originalLedgerId`.
      - **Safety Rule 1 (Single-sided transactions only):** Strictly prohibited reversing complex multi-legged transactions (Pick, Putaway, Transfer). Only allowed single-sided entries (such as erroneous manual count adjustments `ADJUST_IN`/`ADJUST_OUT`).
      - **Safety Rule 2 (No subsequent movement):** Inspected transaction history for the related inventory row; if later movements occurred, rejected the request to prevent cascading balance errors.
    - **Implemented Update Request API (`PUT /api/reversals/requests/{id}`):** Restricted reason edits to `PENDING` status and enforced that the requester matches `requestedBy`.
    - **Implemented Admin Approval API (`POST /api/reversals/requests/{id}/approve`):**
      - Executed within a Prisma `$transaction`: Updated status to `APPROVED`, inserted a new opposite-signed ledger entry of type `REVERSAL` with `reversalOfId` referencing the original row (preserving append-only ledger integrity without deleting/modifying history), and restored inventory balances.
    - **Implemented Admin Rejection API (`POST /api/reversals/requests/{id}/reject`):** Updated status to `REJECTED` and saved `reviewNote`.
  - **Quick Adjustments Module:**

    - **Draft Creation (`POST /api/adjustments`):** Created draft adjustments saving `proposedBy` and a snapshot of `inventoryVersion` to guard against concurrency conflicts.
    - **Submission (`POST /api/adjustments/{id}/submit`):** Transitioned status to `PENDING_APPROVAL`.
    - **Approval (`POST /api/adjustments/{id}/approve`):** Enforced transactional validation: approver must differ from creator (`approvedBy != proposedBy`), checked `inventoryVersion` (throwing `409 Conflict` if the record was modified concurrently), updated inventory, and logged an `ADJUST_IN`/`ADJUST_OUT` ledger entry.
- **Week 4 Wrap-Up:**

  - Concluded a highly productive week: fully achieved Demo 1 sign-off and successfully delivered core foundational services for Demo 2.
  - Well-positioned to tackle STAGING and TRANSIT operations alongside full E2E testing next week!
