# Product Listing Module Test Cases

## Test Suite Information
| Field | Value |
|-------|-------|
| Module | Product Listing |
| Version | 1.0 |
| Created By | QA Team |
| Last Updated | January 2024 |

---

## Test Cases

### TC_PROD_001: Display All Products
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products exist in database, User is on home page |
| **Test Steps** | 1. Navigate to Products page 2. Verify products are displayed |
| **Test Data** | N/A |
| **Expected Result** | All products displayed with image, name, price |

---

### TC_PROD_002: Product Search by Name
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products exist in catalog |
| **Test Steps** | 1. Enter product name in search 2. Click Search/Press Enter |
| **Test Data** | Search: "Laptop" |
| **Expected Result** | Products matching "Laptop" are displayed |

---

### TC_PROD_003: Search with No Results
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Negative |
| **Preconditions** | User is on products page |
| **Test Steps** | 1. Enter non-existent product name 2. Click Search |
| **Test Data** | Search: "XYZABC123" |
| **Expected Result** | "No products found" message displayed |

---

### TC_PROD_004: Filter by Category
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products with categories exist |
| **Test Steps** | 1. Click on Category dropdown 2. Select "Electronics" |
| **Test Data** | Category: Electronics |
| **Expected Result** | Only electronics products displayed |

---

### TC_PROD_005: Filter by Price Range
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products exist with various prices |
| **Test Steps** | 1. Set min price 2. Set max price 3. Apply filter |
| **Test Data** | Min: $100, Max: $500 |
| **Expected Result** | Only products in $100-$500 range displayed |

---

### TC_PROD_006: Sort by Price Low to High
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Multiple products displayed |
| **Test Steps** | 1. Click Sort dropdown 2. Select "Price: Low to High" |
| **Test Data** | N/A |
| **Expected Result** | Products sorted by price ascending |

---

### TC_PROD_007: Sort by Price High to Low
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Multiple products displayed |
| **Test Steps** | 1. Click Sort dropdown 2. Select "Price: High to Low" |
| **Test Data** | N/A |
| **Expected Result** | Products sorted by price descending |

---

### TC_PROD_008: Sort by Newest First
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Multiple products displayed |
| **Test Steps** | 1. Click Sort dropdown 2. Select "Newest First" |
| **Test Data** | N/A |
| **Expected Result** | Products sorted by date descending |

---

### TC_PROD_009: Product Details Page
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products displayed on listing page |
| **Test Steps** | 1. Click on any product card |
| **Test Data** | Product: Sample Laptop |
| **Expected Result** | Product detail page opens with full info |

---

### TC_PROD_010: Product Image Gallery
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Product has multiple images |
| **Test Steps** | 1. Open product detail 2. Click on thumbnail images |
| **Test Data** | N/A |
| **Expected Result** | Main image changes to clicked thumbnail |

---

### TC_PROD_011: Out of Stock Display
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Product with 0 inventory exists |
| **Test Steps** | 1. Navigate to out of stock product |
| **Test Data** | Product with quantity: 0 |
| **Expected Result** | "Out of Stock" badge displayed, Add to Cart disabled |

---

### TC_PROD_012: Pagination
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | More than 20 products exist |
| **Test Steps** | 1. Navigate to products page 2. Click page 2 |
| **Test Data** | N/A |
| **Expected Result** | Next set of products displayed |

---

### TC_PROD_013: Products Per Page
| Field | Details |
|-------|---------|
| **Priority** | Low |
| **Test Type** | Positive |
| **Preconditions** | Multiple products exist |
| **Test Steps** | 1. Change "Show" dropdown to 48 |
| **Test Data** | Show: 48 |
| **Expected Result** | 48 products displayed per page |

---

### TC_PROD_014: Multiple Filters Combined
| Field | Details |
|-------|---------|
| **Priority** | High |
| **Test Type** | Positive |
| **Preconditions** | Products with various attributes exist |
| **Test Steps** | 1. Select category 2. Set price range 3. Select brand |
| **Test Data** | Category: Electronics, Price: $100-$500, Brand: Samsung |
| **Expected Result** | Only products matching all filters displayed |

---

### TC_PROD_015: Clear All Filters
| Field | Details |
|-------|---------|
| **Priority** | Medium |
| **Test Type** | Positive |
| **Preconditions** | Filters are applied |
| **Test Steps** | 1. Click "Clear All" filters |
| **Test Data** | N/A |
| **Expected Result** | All filters removed, all products displayed |

---

## Summary

| Category | Count |
|----------|-------|
| Total Test Cases | 15 |
| Positive Tests | 14 |
| Negative Tests | 1 |
| High Priority | 7 |
| Medium Priority | 6 |
| Low Priority | 2 |

---

*Note: This is a markdown representation. For actual Excel format, export this to .xlsx file.*
