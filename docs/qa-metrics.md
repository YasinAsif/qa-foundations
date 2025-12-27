# QA Metrics and KPIs

## Overview

Quality Assurance metrics (key performance indicators) are quantitative measures used to track and assess the quality of software testing processes and outcomes. These metrics help teams make data-driven decisions and improve their testing effectiveness.

---

## Categories of QA Metrics

```
┌─────────────────────────────────────────────────────────────────┐
│                    QA METRICS CATEGORIES                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌──────────────────┐    ┌──────────────────┐                 │
│   │   TEST METRICS   │    │  DEFECT METRICS  │                 │
│   │                  │    │                  │                 │
│   │ - Execution Rate │    │ - Defect Density │                 │
│   │ - Pass/Fail Rate │    │ - Defect Leakage │                 │
│   │ - Coverage %     │    │ - Defect Age     │                 │
│   │ - Automation %   │    │ - Defect Removal │                 │
│   └──────────────────┘    └──────────────────┘                 │
│                                                                 │
│   ┌──────────────────┐    ┌──────────────────┐                 │
│   │ PROCESS METRICS  │    │ PRODUCT METRICS  │                 │
│   │                  │    │                  │                 │
│   │ - Cycle Time     │    │ - Customer Bugs  │                 │
│   │ - Test Efficiency│    │ - Availability   │                 │
│   │ - Review Effort  │    │ - MTBF/MTTR      │                 │
│   │ - Cost per Bug   │    │ - User Satisfaction│               │
│   └──────────────────┘    └──────────────────┘                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 1. Test Execution Metrics

### Test Case Execution Rate

**Definition:** Percentage of test cases executed against total planned.

```
Formula: (Executed Test Cases / Total Test Cases) x 100
```

| Status | Count | Percentage |
|--------|-------|------------|
| Executed | 450 | 90% |
| Not Executed | 50 | 10% |
| **Total** | **500** | **100%** |

---

### Test Case Pass Rate

**Definition:** Percentage of test cases that passed.

```
Formula: (Passed Test Cases / Executed Test Cases) x 100
```

| Status | Count | Percentage |
|--------|-------|------------|
| Passed | 405 | 90% |
| Failed | 45 | 10% |
| **Total Executed** | **450** | **100%** |

---

### Test Case Effectiveness

**Definition:** Ability of test cases to find defects.

```
Formula: (Defects Found / Test Cases Executed) x 100
```

**Interpretation:**
- Higher % = More effective tests
- Optimal range: 20-30% for new features
- Lower % expected for mature products

---

## 2. Defect Metrics

### Defect Density

**Definition:** Number of defects per unit size of software.

```
Formula: Total Defects / Size of Software (KLOC or Function Points)

Example: 50 defects / 10 KLOC = 5 defects per KLOC
```

**Industry Benchmarks:**
| Quality Level | Defects per KLOC |
|---------------|------------------|
| World Class | < 1 |
| Good | 1 - 5 |
| Average | 5 - 10 |
| Poor | > 10 |

---

### Defect Severity Distribution

```
┌─────────────────────────────────────────────────────────────────┐
│               DEFECT SEVERITY DISTRIBUTION                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   Critical  ########                           15%              │
│   High      ##############                     25%              │
│   Medium    ########################           40%              │
│   Low       ############                       20%              │
│                                                                 │
│   0%    20%    40%    60%    80%    100%                       │
└─────────────────────────────────────────────────────────────────┘
```

| Severity | Count | Percentage | Target |
|----------|-------|------------|--------|
| Critical | 8 | 15% | < 5% |
| High | 13 | 25% | < 20% |
| Medium | 21 | 40% | 40-50% |
| Low | 10 | 20% | 30-40% |

---

### Defect Leakage

**Definition:** Defects found in production that escaped testing.

```
Formula: (Production Defects / Total Defects Found) x 100
```

| Phase | Defects Found |
|-------|---------------|
| Development | 30 |
| QA | 45 |
| UAT | 15 |
| Production | 10 |
| **Total** | **100** |

**Defect Leakage = (10 / 100) x 100 = 10%**

**Target:** < 5% defect leakage to production

---

### Defect Removal Efficiency (DRE)

**Definition:** Percentage of defects found before production.

```
Formula: (Defects Found Before Release / Total Defects) x 100
```

**Example:**
- Pre-release defects: 90
- Production defects: 10
- DRE = (90 / 100) x 100 = **90%**

**Target:** DRE > 95%

---

### Defect Age

**Definition:** Average time a defect remains open.

```
Formula: Sum of (Closed Date - Open Date) / Number of Defects
```

| Priority | Avg Age (Days) | Target |
|----------|----------------|--------|
| Critical | 1 | < 1 day |
| High | 3 | < 3 days |
| Medium | 7 | < 7 days |
| Low | 14 | < 14 days |

---

## 3. Test Coverage Metrics

### Requirements Coverage

**Definition:** Percentage of requirements covered by test cases.

```
Formula: (Requirements with Test Cases / Total Requirements) x 100
```

```
┌────────────────────────────────────────────────────────────────┐
│                  REQUIREMENTS COVERAGE                         │
├────────────────────────────────────────────────────────────────┤
│                                                                │
│   Covered       ####################################   95%     │
│   Not Covered   ##                                     5%      │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

---

### Code Coverage

**Definition:** Percentage of code executed during testing.

| Coverage Type | Description | Target |
|---------------|-------------|--------|
| Line Coverage | Lines executed | > 80% |
| Branch Coverage | Decision branches taken | > 75% |
| Function Coverage | Functions called | > 90% |
| Path Coverage | Execution paths | > 70% |

---

## 4. Automation Metrics

### Test Automation Coverage

**Definition:** Percentage of test cases automated.

```
Formula: (Automated Test Cases / Total Test Cases) x 100
```

| Category | Total | Automated | Coverage |
|----------|-------|-----------|----------|
| Regression | 200 | 180 | 90% |
| Smoke | 50 | 50 | 100% |
| Functional | 300 | 150 | 50% |
| **Total** | **550** | **380** | **69%** |

---

### Automation ROI

**Definition:** Return on investment from test automation.

```
Formula: ((Manual Cost - Automation Cost) / Automation Cost) x 100

Where:
- Manual Cost = Manual Execution Time x Hourly Rate x Number of Runs
- Automation Cost = Development Cost + Maintenance Cost + Execution Cost
```

---

## 5. Process Metrics

### Test Cycle Time

```
┌─────────────────────────────────────────────────────────────────┐
│                    TEST CYCLE TIMELINE                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   Planning    Development    Execution    Reporting             │
│   --------    -----------    ---------    ---------             │
│    3 days       5 days        7 days       2 days               │
│                                                                 │
│   |----------------------------------------------|              │
│                     17 days total                               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

### Test Efficiency

**Definition:** Ratio of productive testing time to total time.

```
Formula: (Actual Test Execution Time / Total Testing Time) x 100
```

| Activity | Hours | Percentage |
|----------|-------|------------|
| Test Execution | 40 | 50% |
| Environment Setup | 16 | 20% |
| Defect Analysis | 12 | 15% |
| Meetings | 8 | 10% |
| Documentation | 4 | 5% |
| **Total** | **80** | **100%** |

---

## 6. Key Performance Indicators (KPIs)

### QA Dashboard Metrics

```
┌─────────────────────────────────────────────────────────────────┐
│                    QA DASHBOARD                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│   │  Pass Rate   │  │  Defect      │  │  Coverage    │         │
│   │    92%       │  │  Leakage 3%  │  │    95%       │         │
│   │   +2%        │  │   -1%        │  │   +5%        │         │
│   └──────────────┘  └──────────────┘  └──────────────┘         │
│                                                                 │
│   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│   │  Automation  │  │  DRE         │  │  Cycle Time  │         │
│   │    75%       │  │   97%        │  │   12 days    │         │
│   │   +10%       │  │   +2%        │  │   -3 days    │         │
│   └──────────────┘  └──────────────┘  └──────────────┘         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Critical KPIs Summary

| KPI | Definition | Target | Frequency |
|-----|------------|--------|-----------|
| **Test Pass Rate** | Passed/Executed tests | > 95% | Daily |
| **Defect Leakage** | Production defects | < 5% | Per Release |
| **DRE** | Pre-release defects found | > 95% | Per Release |
| **Requirements Coverage** | Requirements with tests | 100% | Per Sprint |
| **Automation Coverage** | Automated tests | > 70% | Monthly |
| **Cycle Time** | Test completion time | Decreasing | Per Sprint |
| **Defect Age** | Time to close defects | Per severity | Weekly |

---

## 7. Reporting Templates

### Sprint Quality Report

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Test Cases Executed | 100% | 98% | At Risk |
| Pass Rate | > 95% | 92% | At Risk |
| Defects Found | N/A | 25 | Info |
| Critical Defects Open | 0 | 0 | On Track |
| Automation Coverage | > 70% | 75% | On Track |
| Defect Leakage | < 5% | 2% | On Track |

### Status Legend:
- On Track - Meeting targets
- At Risk - Needs attention
- Off Track - Requires immediate action
- Info - Informational only

---

## 8. Best Practices

### Choosing Metrics

1. **Align with Goals** - Choose metrics that support project objectives
2. **Keep it Simple** - Don't track too many metrics
3. **Make it Actionable** - Metrics should drive decisions
4. **Automate Collection** - Use tools for consistent data
5. **Review Regularly** - Analyze trends, not just numbers

### Common Pitfalls to Avoid

1. **Vanity Metrics** - Metrics that look good but don't help
2. **Gaming Metrics** - Optimizing for numbers, not quality
3. **Too Many Metrics** - Analysis paralysis
4. **Ignoring Context** - Numbers without understanding
5. **Static Targets** - Not adjusting goals over time

---

## Metrics Calculation Cheat Sheet

| Metric | Formula |
|--------|---------|
| Execution Rate | (Executed / Total) x 100 |
| Pass Rate | (Passed / Executed) x 100 |
| Defect Density | Defects / KLOC |
| Defect Leakage | (Prod Defects / Total) x 100 |
| DRE | (Pre-Prod Defects / Total) x 100 |
| Coverage | (Covered Items / Total Items) x 100 |
| Automation % | (Auto Tests / Total Tests) x 100 |
| MTBF | Total Operating Time / Number of Failures |
| MTTR | Total Repair Time / Number of Repairs |
