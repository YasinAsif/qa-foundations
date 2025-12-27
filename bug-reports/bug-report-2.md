# Bug Report #2

## Bug ID: BUG-002

## Summary
Product price displays incorrectly when currency is changed

---

## Details

| Field | Value |
|-------|-------|
| **Reported By** | QA Tester |
| **Reported Date** | 2024-01-16 |
| **Severity** | Critical |
| **Priority** | P1 |
| **Status** | In Progress |
| **Assigned To** | Backend Team |
| **Module** | Product Listing |
| **Environment** | All browsers, All devices |

---

## Description

When users change the currency from USD to EUR or other currencies, the product prices are not converted correctly. The conversion rate appears to be inverted, showing significantly higher or lower prices than expected.

---

## Steps to Reproduce

1. Navigate to the product listing page
2. Note the price of any product (e.g., $100.00 USD)
3. Click on the currency selector in the header
4. Select "EUR" from the dropdown
5. Observe the converted price

---

## Expected Result

- Price should be converted using the correct exchange rate
- $100.00 USD should be approximately 92.00 EUR (at rate 0.92)
- Currency symbol should change to the Euro symbol

---

## Actual Result

- Price shows 108.70 EUR instead of 92.00 EUR
- The conversion appears to use the inverse of the actual rate
- This results in prices that are approximately 18% higher than they should be

---

## Test Data

| Original Price (USD) | Expected (EUR) | Actual (EUR) | Variance |
|---------------------|----------------|--------------|----------|
| $100.00 | 92.00 | 108.70 | +18.15% |
| $250.00 | 230.00 | 271.74 | +18.15% |
| $49.99 | 45.99 | 54.33 | +18.13% |

---

## Impact Analysis

### Business Impact

- **Critical** - Customers may be overcharged if they proceed to purchase
- **Legal Risk** - Price misrepresentation could lead to legal issues
- **Trust** - Customer trust will be severely impacted

### User Impact

- Affects all users who change currency
- Estimated 30% of users use non-USD currency

---

## Additional Information

### API Response
```json
{
  "product_id": "PROD-001",
  "base_price": 100.00,
  "base_currency": "USD",
  "converted_price": 108.70,
  "target_currency": "EUR",
  "exchange_rate": 1.087
}
```

### Expected API Response
```json
{
  "product_id": "PROD-001",
  "base_price": 100.00,
  "base_currency": "USD",
  "converted_price": 92.00,
  "target_currency": "EUR",
  "exchange_rate": 0.92
}
```

---

## Probable Root Cause

The conversion formula appears to be:
- **Current:** `converted_price = base_price * (1 / exchange_rate)`
- **Should be:** `converted_price = base_price * exchange_rate`

---

## Attachments

- Screenshot showing incorrect price
- API response logs
- Exchange rate source data

---

## Fix Verification Checklist

| Check | Status |
|-------|--------|
| Verify USD to EUR conversion | Pending |
| Verify USD to GBP conversion | Pending |
| Verify USD to JPY conversion | Pending |
| Verify reverse conversions | Pending |
| Test on cart page | Pending |
| Test on checkout page | Pending |
| Regression test passed | Pending |
