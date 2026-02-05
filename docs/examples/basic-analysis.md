# Basic Analysis Example (Explainable)

Pseudo-code using pandas to compute key metrics.

```python
import pandas as pd
from datetime import date

df = pd.read_csv("data/templates/pending-bills.csv")

df["invoice_date"] = pd.to_datetime(df["invoice_date"])
df["due_date"] = pd.to_datetime(df["due_date"])
today = pd.to_datetime(date.today())

df["days_overdue"] = (today - df["due_date"]).dt.days
df["days_overdue"] = df["days_overdue"].clip(lower=0)

totals = {
    "total_invoiced": df["invoice_amount_kes"].sum(),
    "total_paid": df["amount_paid_kes"].sum(),
    "total_outstanding": df["balance_kes"].sum(),
    "invoice_count": df["invoice_id"].nunique(),
}

aging = pd.cut(
    df["days_overdue"],
    bins=[-1, 30, 90, 180, 10**6],
    labels=["1-30", "31-90", "91-180", "180+"]
)

aging_summary = df.groupby(aging)["balance_kes"].sum()

dept_summary = df.groupby("department").agg(
    outstanding_kes=("balance_kes", "sum"),
    invoice_count=("invoice_id", "nunique")
)

print(totals)
print(aging_summary)
print(dept_summary)
