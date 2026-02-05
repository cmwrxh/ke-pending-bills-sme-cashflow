# Validation Rules — Pending Bills Dataset

Use these rules to ensure the dataset is clean and auditable.

## Required fields
- invoice_id
- supplier_name
- department
- invoice_date
- invoice_amount_kes
- status

## Date rules
- `invoice_date` must be <= today
- `due_date` should be >= invoice_date
- Flag invoices older than 90 days past due

## Amount rules
- invoice_amount_kes >= 0
- amount_paid_kes >= 0
- balance_kes = invoice_amount_kes - amount_paid_kes
- Flag negative balances

## Duplicate rules
- invoice_id must be unique
- Flag duplicates with same supplier + amount + invoice_date

## Status rules
Allowed status values:
- unpaid
- partially_paid
- paid
- disputed

Status logic:
- unpaid → amount_paid_kes = 0
- paid → balance_kes = 0
- partially_paid → 0 < balance_kes < invoice_amount_kes

## Audit trail requirements
- Every update must include a note or reference evidence link
- Keep supporting documents in `/evidence/`
