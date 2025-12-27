# 🐛 Bug Report #3

## Bug ID: BUG-003

## Summary
Shopping cart loses items after user session timeout

---

## Details

| Field | Value |
|-------|-------|
| **Reported By** | QA Tester |
| **Reported Date** | 2024-01-17 |
| **Severity** | Medium |
| **Priority** | P2 |
| **Status** | Fixed |
| **Assigned To** | Full Stack Team |
| **Module** | Shopping Cart |
| **Environment** | All browsers |
| **Fixed Version** | v2.3.5 |

---

## Description

When a user's session times out (after 30 minutes of inactivity), items in their shopping cart are completely lost. After re-login, the cart shows empty even though items were not removed by the user.

---

## Steps to Reproduce

1. Log into the application
2. Add 3-5 items to the shopping cart
3. Verify items appear in the cart
4. Wait for 30+ minutes (session timeout) without any activity
5. Try to access any page - system redirects to login
6. Log in again with the same credentials
7. Navigate to the shopping cart

---

## Expected Result

- Cart items should be persisted in the database
- After re-login, previously added items should still be in the cart
- Cart icon should show the correct count of items

---

## Actual Result

- Shopping cart is empty after re-login
- All previously added items are lost
- Cart icon shows 0 items
- No indication that items were removed

---

## Technical Analysis

### Session Storage Flow
```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   User      │────►│   Session   │────►│  Database   │
│ Adds Item   │     │   Storage   │     │   (cart)    │
└─────────────┘     └──────┬──────┘     └─────────────┘
                          │
                          │ Session Timeout
                          ▼
                   ┌─────────────┐
                   │  Session    │
                   │  Cleared    │
                   └──────┬──────┘
                          │
                          │ ❌ Cart reference lost!
                          ▼
                   ┌─────────────┐
                   │  Empty Cart │
                   └─────────────┘
```

### Code Location
- File: `src/services/cartService.js`
- Function: `syncCartWithSession()`
- Line: 142-156

---

## Root Cause (Developer Notes)

Cart items were being stored with the session ID as a foreign key. When the session expired, the cart-session mapping was invalidated, making items inaccessible even though they existed in the database.

**Fix Applied:** Changed cart storage to use user ID instead of session ID as the primary reference.

---

## Affected User Journeys

1. ❌ Guest user adding items → session timeout → items lost
2. ❌ Logged user adding items → session timeout → items lost
3. ✅ Logged user adding items → active session → items retained

---

## Fix Implementation

```diff
// cartService.js
- const cart = await Cart.findOne({ sessionId: session.id });
+ const cart = await Cart.findOne({ userId: user.id, status: 'active' });

- async function createCart(sessionId) {
-   return await Cart.create({ sessionId, items: [] });
+ async function createCart(userId) {
+   return await Cart.create({ userId, items: [], status: 'active' });
  }
```

---

## Verification Results

| Test Scenario | Before Fix | After Fix |
|--------------|------------|-----------|
| Session timeout - logged user | ❌ Cart empty | ✅ Cart retained |
| Session timeout - guest user | ❌ Cart empty | ✅ Cart retained* |
| Manual logout | ✅ Cart retained | ✅ Cart retained |
| Browser close/reopen | ❌ Cart empty | ✅ Cart retained |

*Guest cart is now saved with browser fingerprint

---

## Regression Testing

| Test Case | Status |
|-----------|--------|
| Add item to cart | ✅ Pass |
| Remove item from cart | ✅ Pass |
| Update item quantity | ✅ Pass |
| Cart persistence across sessions | ✅ Pass |
| Cart merge on login | ✅ Pass |
| Checkout flow | ✅ Pass |

---

## Sign-off

| Role | Name | Date | Status |
|------|------|------|--------|
| Developer | John Doe | 2024-01-18 | ✅ Fixed |
| QA | Jane Smith | 2024-01-19 | ✅ Verified |
| Product Owner | Bob Johnson | 2024-01-19 | ✅ Approved |
