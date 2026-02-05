# Metrics Specification — Pending Bills & SME Cashflow

Purpose: define consistent metrics for reporting and dashboards.

---

## 1) Core totals
- **Total invoiced (KES)** = SUM(invoice_amount_kes)
- **Total paid (KES)** = SUM(amount_paid_kes)
- **Total outstanding (KES)** = SUM(balance_kes)
- **Invoice count** = COUNT(invoice_id)

---

## 2) Aging buckets (by days overdue)

Days overdue = today − due_date

Buckets:
- Current (≤ 0 days)
- 1–30 days
- 31–90 days
- 91–180 days
- 180+ days

Report:
- Count of invoices per bucket
- Outstanding KES per bucket

---

## 3) Department / Agency breakdown
For each `department`:
- Total invoiced
- Total paid
- Outstanding KES
- Average days overdue

---

## 4) Supplier concentration
- Outstanding KES by supplier
- Top 10 suppliers by outstanding balance
- Share of total outstanding by top suppliers

---

## 5) Payment performance
- % paid on time
- Average days to payment
- Median days to payment

---

## 6) SME impact indicators (optional tags)
If SME flag exists:
- Outstanding KES for SMEs
- SME invoice aging vs large suppliers

---

## 7) Data quality indicators
- % invoices missing due_date
- Duplicate invoice count
- Evidence coverage rate (notes/evidence present)
