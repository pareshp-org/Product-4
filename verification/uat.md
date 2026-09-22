# UAT Runbook — Product-4 (Billing & Invoicing)

## Feature
Automated invoice generation and payment recording

## Preconditions
- Service is configured with valid environment (`.env.local` or `.env.example`).
- Database migrations have been applied via `make migrate`.
- Required port is free and accessible.

## Steps
1. Start Product-4 on port 8084
2. Query GET /health to ensure billing ledger schema is active
3. Post invoice generation request via POST /api/v1/invoices
4. Query GET /api/v1/invoices to verify invoice total and status

## Expected Results
- Billing service reports healthy status
- Invoice record is generated with invoice ID, amount, and 'pending' status

---
*Author: QA & Primary Owner (MasterSpec Section 31.1, Section 33.1)*
*Verification Contract: `verification/contract.yaml`*
