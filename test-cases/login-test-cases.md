# Login Module Test Cases

## Test Suite Information
| Field | Value |
|-------|-------|
| Module | Authentication - Login |
| Version | 1.0 |
| Created By | QA Team |
| Last Updated | January 2024 |

---

## Test Cases

### TC_LOGIN_001: Valid Login with Correct Credentials
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | User account exists, User is on login page |
| **Test Steps** | 1. Enter valid username 2. Enter valid password 3. Click Login |
| **Test Data** | Username: testuser@email.com, Password: Test@123 |
| **Expected Result** | User successfully logged in and redirected to dashboard |

---

### TC_LOGIN_002: Invalid Login with Wrong Password
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | User account exists, User is on login page |
| **Test Steps** | 1. Enter valid username 2. Enter incorrect password 3. Click Login |
| **Test Data** | Username: testuser@email.com, Password: WrongPass123 |
| **Expected Result** | Error message: "Invalid credentials. Please try again." |

---

### TC_LOGIN_003: Login with Unregistered Email
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Negative |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Enter unregistered email 2. Enter any password 3. Click Login |
| **Test Data** | Username: notexist@email.com, Password: AnyPass123 |
| **Expected Result** | Error message: "Account not found. Please register." |

---

### TC_LOGIN_004: Login with Empty Username
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Negative |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Leave username empty 2. Enter password 3. Click Login |
| **Test Data** | Username: (empty), Password: Test@123 |
| **Expected Result** | Validation error: "Username is required" |

---

### TC_LOGIN_005: Login with Empty Password
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Negative |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Enter username 2. Leave password empty 3. Click Login |
| **Test Data** | Username: testuser@email.com, Password: (empty) |
| **Expected Result** | Validation error: "Password is required" |

---

### TC_LOGIN_006: Login with Remember Me Checked
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | User account exists, User is on login page |
| **Test Steps** | 1. Enter valid credentials 2. Check "Remember Me" 3. Click Login 4. Close browser 5. Reopen and visit site |
| **Test Data** | Username: testuser@email.com, Password: Test@123 |
| **Expected Result** | User remains logged in after browser restart |

---

### TC_LOGIN_007: Password Visibility Toggle
| Field | Details |
|-------|---------|
| **Priority** | Low |
| **Test Type** | Positive |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Enter password 2. Click show/hide password icon 3. Verify password visibility toggles |
| **Test Data** | Password: Test@123 |
| **Expected Result** | Password shows as plain text when visible, dots when hidden |

---

### TC_LOGIN_008: Forgot Password Link
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Click "Forgot Password?" link |
| **Test Data** | N/A |
| **Expected Result** | User is redirected to password reset page |

---

### TC_LOGIN_009: Account Lockout After Failed Attempts
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Security |
| **Preconditions** | User account exists |
| **Test Steps** | 1. Enter valid username 2. Enter wrong password 3. Click Login 4. Repeat 5 times |
| **Test Data** | Username: testuser@email.com, Password: Wrong1, Wrong2... |
| **Expected Result** | Account locked after 5 failed attempts, error message displayed |

---

### TC_LOGIN_010: SQL Injection Prevention
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Security |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Enter SQL injection in username 2. Enter any password 3. Click Login |
| **Test Data** | Username: ' OR '1'='1, Password: anything |
| **Expected Result** | Login fails, no unauthorized access, input is sanitized |

---

### TC_LOGIN_011: XSS Prevention
| Field | Details |
|-------|---------|
| **Priority** | Critical |
| **Test Type** | Security |
| **Preconditions** | User is on login page |
| **Test Steps** | 1. Enter XSS script in username field 2. Submit form |
| **Test Data** | Username: <script>alert('xss')</script> |
| **Expected Result** | Script is not executed, input is properly escaped |

---

### TC_LOGIN_012: Session Timeout
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | User is logged in |
| **Test Steps** | 1. Login successfully 2. Wait for session timeout (30 min) 3. Try to access a page |
| **Test Data** | N/A |
| **Expected Result** | User is redirected to login page with session expired message |

---

## Summary

| Category | Count |
|----------|-------|
| Total Test Cases | 12 |
| Positive Tests | 5 |
| Negative Tests | 4 |
| Security Tests | 3 |
| High Priority | 6 |
| Medium Priority | 4 |
| Low Priority | 1 |
| Critical Priority | 2 |

---

*Note: This is a markdown representation. For actual Excel format, export this to .xlsx file.*
