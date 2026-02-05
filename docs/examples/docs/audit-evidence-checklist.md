# Governance & Audit Evidence Checklist — Pending Bills

Use this checklist to ensure transparency, traceability, and audit readiness.

---

## 1) Invoice evidence
- [ ] Invoice document stored
- [ ] Purchase Order / LPO stored
- [ ] Delivery or service completion note stored
- [ ] Contract or approval email (if applicable)

---

## 2) Payment evidence (if paid or partially paid)
- [ ] Payment advice / remittance stored
- [ ] Bank statement reference stored
- [ ] Payment date recorded in dataset

---

## 3) Dataset integrity
- [ ] `invoice_id` unique and matches invoice
- [ ] Amounts reconcile (invoice = paid + balance)
- [ ] Status matches amount logic
- [ ] Due dates verified

---

## 4) Aging & classification
- [ ] Days overdue computed correctly
- [ ] Aging bucket assigned consistently
- [ ] Disputed invoices tagged with notes/evidence

---

## 5) Change / update trail
- [ ] Update includes date and owner
- [ ] Notes reference evidence location (e.g., `evidence/INV-0001/*`)
- [ ] Previous values preserved or versioned (if possible)

---

## 6) Access & governance
- [ ] Edit access restricted to authorized users
- [ ] Read-only view available for reporting
- [ ] Periodic review schedule defined (e.g., monthly)

---

## 7) Reporting readiness
- [ ] Core totals validated against source systems
- [ ] Department and supplier summaries reviewed
- [ ] Data quality indicators reviewed
