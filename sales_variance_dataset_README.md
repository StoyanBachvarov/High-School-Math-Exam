# Synthetic Sales Variance Dataset

Columns: `Year | Customer | Product | Quantity | Price | Sales`

Open the Excel file in Google Sheets, or import the UTF-8 CSV. The `Sales_Data` worksheet contains the table; `Dataset_Notes` explains its assumptions.

**Purpose:** Synthetic educational data for price and Volume/Mix analysis; not actual customer sales.

**Structure:** 100 customers x 5 products x 2 years = 1,000 rows; one row per year/customer/product.

**Years:** 2025 is the previous period; 2026 is a simulated full current year, not year-to-date data.

**Currency and units:** Prices and sales are in EUR. Quantity is a count of standardized units; all quantities are positive integers.

**Customer scope:** Each Customer identifier represents one customer site. All 500 customer-product relationships are assumed established for more than 12 months before 2025 and comparable across both years.

**Business scope:** All customers buy all five products in each year. There is no new/lost business, currency movement, scope change, tax, return, discount line or fixed charge.

**Price definition:** Price is the effective annual unit price for the customer-product pair. Any negotiated discount is already included.

**Sales definition:** Sales = Quantity x Price exactly, using prices to two decimal places. There are no separate fixed charges.

**Later analysis:** Calculate price and volume effects at the customer-product level, then sum by customer, product and overall. Customer-specific prices and changing mix make simple averages misleading.

**Weighted prices:** If an aggregated unit price is needed, calculate total Sales / total Quantity, not the arithmetic mean of Price. Use pair-level effects for the supplied variance methodology.

**Variation:** The dataset contains increasing, decreasing and unchanged prices and quantities. Customer-specific negotiated prices and product/customer growth patterns create mix variation.

**Reproducibility:** Generated with Python random.Random using seed 20261114.

## Validation totals

| Year | Rows | Sales (EUR) |
|---|---:|---:|
| 2025 | 500 | 2,708,174.76 |
| 2026 | 500 | 2,970,470.37 |

## Customer-product changes between years

| Measure | Increase | Decrease | Unchanged |
|---|---:|---:|---:|
| Price | 315 | 112 | 73 |
| Quantity | 285 | 168 | 47 |
