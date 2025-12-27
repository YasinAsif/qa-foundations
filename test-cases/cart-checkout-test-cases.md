# Cart & Checkout Module Test Cases

## Test Suite Information
| Field | Value |
|-------|-------|
| Module | Shopping Cart & Checkout |
| Version | 1.0 |
| Created By | QA Team |
| Last Updated | January 2024 |

---

## Shopping Cart Test Cases

### TC_CART_001: Add Product to Cart
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Positive |
| **Preconditions** | User is logged in, Product is in stock |
| **Test Steps** | 1. Navigate to product page 2. Click "Add to Cart" |
| **Test Data** | Product: Sample Product, Qty: 1 |
| **Expected Result** | Product added to cart, cart count updated |

---

### TC_CART_002: Add Multiple Products
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | User is logged in |
| **Test Steps** | 1. Add Product A 2. Add Product B 3. View cart |
| **Test Data** | Product A, Product B |
| **Expected Result** | Both products appear in cart with correct details |

---

### TC_CART_003: Update Quantity
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Product is in cart |
| **Test Steps** | 1. Go to cart 2. Change quantity from 1 to 3 3. Update |
| **Test Data** | New Qty: 3 |
| **Expected Result** | Quantity updated, subtotal recalculated |

---

### TC_CART_004: Remove Item from Cart
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Product is in cart |
| **Test Steps** | 1. Go to cart 2. Click Remove/Delete on item |
| **Test Data** | N/A |
| **Expected Result** | Item removed, cart total updated |

---

### TC_CART_005: Empty Cart Message
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Cart is empty |
| **Test Steps** | 1. Navigate to cart page |
| **Test Data** | N/A |
| **Expected Result** | "Your cart is empty" message with shop link |

---

### TC_CART_006: Cart Persistence
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | User logged in, items in cart |
| **Test Steps** | 1. Add items 2. Logout 3. Login again 4. View cart |
| **Test Data** | N/A |
| **Expected Result** | Previously added items still in cart |

---

### TC_CART_007: Apply Valid Coupon
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Items in cart, valid coupon exists |
| **Test Steps** | 1. Enter coupon code 2. Click Apply |
| **Test Data** | Coupon: SAVE10 (10% off) |
| **Expected Result** | Discount applied, total reduced by 10% |

---

### TC_CART_008: Apply Invalid Coupon
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Negative |
| **Preconditions** | Items in cart |
| **Test Steps** | 1. Enter invalid coupon 2. Click Apply |
| **Test Data** | Coupon: INVALID123 |
| **Expected Result** | Error: "Invalid coupon code" |

---

### TC_CART_009: Apply Expired Coupon
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Negative |
| **Preconditions** | Items in cart |
| **Test Steps** | 1. Enter expired coupon 2. Click Apply |
| **Test Data** | Coupon: OLDCODE (expired) |
| **Expected Result** | Error: "This coupon has expired" |

---

### TC_CART_010: Quantity Exceeds Stock
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | Product with stock: 5 |
| **Test Steps** | 1. Try to add quantity 10 |
| **Test Data** | Stock: 5, Requested: 10 |
| **Expected Result** | Error: "Only 5 items available" |

---

## Checkout Test Cases

### TC_CHKOUT_001: Proceed to Checkout
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Positive |
| **Preconditions** | Items in cart, user logged in |
| **Test Steps** | 1. Click "Proceed to Checkout" |
| **Test Data** | N/A |
| **Expected Result** | User redirected to checkout page |

---

### TC_CHKOUT_002: Add Shipping Address
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Positive |
| **Preconditions** | On checkout page |
| **Test Steps** | 1. Enter full address 2. Click Continue |
| **Test Data** | Name, Street, City, State, ZIP, Phone |
| **Expected Result** | Address saved, proceed to payment |

---

### TC_CHKOUT_003: Invalid Address Fields
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | On checkout page |
| **Test Steps** | 1. Leave required fields empty 2. Click Continue |
| **Test Data** | Empty fields |
| **Expected Result** | Validation errors for required fields |

---

### TC_CHKOUT_004: Select Shipping Method
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Address entered |
| **Test Steps** | 1. View shipping options 2. Select Express Shipping |
| **Test Data** | Shipping: Express ($15) |
| **Expected Result** | Shipping cost added to order total |

---

### TC_CHKOUT_005: Credit Card Payment
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Positive |
| **Preconditions** | On payment step |
| **Test Steps** | 1. Enter card details 2. Click Pay Now |
| **Test Data** | Card: 4242424242424242, Exp: 12/25, CVV: 123 |
| **Expected Result** | Payment successful, order confirmation |

---

### TC_CHKOUT_006: Invalid Card Number
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | On payment step |
| **Test Steps** | 1. Enter invalid card number 2. Click Pay |
| **Test Data** | Card: 1234567890123456 |
| **Expected Result** | Error: "Invalid card number" |

---

### TC_CHKOUT_007: Expired Card
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | On payment step |
| **Test Steps** | 1. Enter expired card date 2. Click Pay |
| **Test Data** | Exp: 01/20 |
| **Expected Result** | Error: "Card has expired" |

---

### TC_CHKOUT_008: PayPal Payment
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | On payment step |
| **Test Steps** | 1. Select PayPal 2. Login to PayPal 3. Confirm |
| **Test Data** | PayPal account |
| **Expected Result** | Payment via PayPal successful |

---

### TC_CHKOUT_009: Order Confirmation Email
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Order completed |
| **Test Steps** | 1. Complete order 2. Check email |
| **Test Data** | N/A |
| **Expected Result** | Order confirmation email received |

---

### TC_CHKOUT_010: Order Summary Display
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Order completed |
| **Test Steps** | 1. View order confirmation page |
| **Test Data** | N/A |
| **Expected Result** | Order number, items, total, shipping address displayed |

---

### TC_CHKOUT_011: Guest Checkout
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | User not logged in, items in cart |
| **Test Steps** | 1. Click Checkout 2. Choose "Guest Checkout" 3. Enter details |
| **Test Data** | Guest email and address |
| **Expected Result** | Guest can complete purchase without account |

---

### TC_CHKOUT_012: Checkout Session Timeout
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | On checkout page |
| **Test Steps** | 1. Leave page idle for 15 min 2. Try to proceed |
| **Test Data** | N/A |
| **Expected Result** | Session warning, redirect to cart |

---

## Summary

| Category | Count |
|----------|-------|
| **Cart Tests** | 10 |
| **Checkout Tests** | 12 |
| **Total Test Cases** | 22 |
| Positive Tests | 16 |
| Negative Tests | 6 |
| Critical Priority | 4 |
| High Priority | 14 |
| Medium Priority | 4 |

---

*Note: This is a markdown representation. For actual Excel format, export this to .xlsx file.*
