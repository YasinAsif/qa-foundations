# Types of Software Testing

## Overview

Software testing can be categorized in multiple ways based on the testing approach, level, and purpose. This document provides a comprehensive guide to different types of testing used in QA.

---

## Testing Levels

```
┌─────────────────────────────────────────────────────────────────┐
│                    TESTING LEVELS PYRAMID                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│                         /\                                      │
│                        /  \                                     │
│                       /    \                                    │
│                      / E2E  \         <-- End-to-End Tests     │
│                     /________\            (Few, Slow, Costly)   │
│                    /          \                                 │
│                   / Integration\       <-- Integration Tests   │
│                  /______________\          (Medium)             │
│                 /                \                              │
│                /   Unit Tests     \    <-- Unit Tests          │
│               /____________________\       (Many, Fast, Cheap)  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 1. Unit Testing

**Definition:** Testing individual components or functions in isolation.

| Aspect | Details |
|--------|---------|
| **Scope** | Single function, method, or class |
| **Who** | Developers |
| **When** | During development |
| **Tools** | JUnit, NUnit, pytest, Jest |

### Example
```javascript
// Function to test
function add(a, b) {
    return a + b;
}

// Unit test
test('adds 1 + 2 to equal 3', () => {
    expect(add(1, 2)).toBe(3);
});
```

---

## 2. Integration Testing

**Definition:** Testing the interaction between integrated units/modules.

| Aspect | Details |
|--------|---------|
| **Scope** | Multiple modules together |
| **Who** | Developers/QA |
| **When** | After unit testing |
| **Tools** | Postman, REST Assured, TestNG |

### Approaches
- **Big Bang** - All modules integrated at once
- **Top-Down** - Testing from top modules to bottom
- **Bottom-Up** - Testing from bottom modules to top
- **Hybrid/Sandwich** - Combination of top-down and bottom-up

```
┌─────────────────────────────────────────────────────┐
│            INTEGRATION TESTING APPROACHES           │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Top-Down           Bottom-Up          Hybrid       │
│      ┌───┐          ┌───┐┌───┐         ┌───┐       │
│      │ A │          │ D ││ E │         │ A │       │
│      └─┬─┘          └─┬─┘└─┬─┘         └─┬─┘       │
│        │              │    │             │         │
│    ┌───┴───┐          └──┬─┘         ┌───┴───┐     │
│  ┌─┴─┐   ┌─┴─┐        ┌──┴──┐      ┌─┴─┐   ┌─┴─┐   │
│  │ B │   │ C │        │  C  │      │ B │   │ C │   │
│  └───┘   └───┘        └──┬──┘      └───┘   └───┘   │
│    |       |             │           ^       ^     │
│  Stubs   Stubs        ┌──┴──┐      ┌─┴─┐   ┌─┴─┐   │
│                       │  B  │      │ D │   │ E │   │
│                       └──┬──┘      └───┘   └───┘   │
│                          │                         │
│                       ┌──┴──┐                      │
│                       │  A  │                      │
│                       └─────┘                      │
│                         ^                          │
│                      Drivers                       │
└─────────────────────────────────────────────────────┘
```

---

## 3. System Testing

**Definition:** Testing the complete, integrated system as a whole.

| Aspect | Details |
|--------|---------|
| **Scope** | Entire application |
| **Who** | QA Team |
| **When** | After integration testing |
| **Tools** | Selenium, Cypress, Playwright |

### Types of System Testing
- Functional Testing
- Performance Testing
- Security Testing
- Usability Testing
- Compatibility Testing

---

## 4. Acceptance Testing

**Definition:** Testing to verify the system meets business requirements.

### Types

| Type | Description | Performed By |
|------|-------------|--------------|
| **UAT** | User Acceptance Testing | End Users |
| **BAT** | Business Acceptance Testing | Business Analysts |
| **OAT** | Operational Acceptance Testing | Operations Team |
| **Alpha** | Testing in controlled environment | Internal Team |
| **Beta** | Testing in real environment | External Users |

---

## Functional vs Non-Functional Testing

```
┌─────────────────────────────────────────────────────────────────┐
│                    TESTING CATEGORIES                           │
├────────────────────────────┬────────────────────────────────────┤
│     FUNCTIONAL TESTING     │     NON-FUNCTIONAL TESTING         │
├────────────────────────────┼────────────────────────────────────┤
│ - Unit Testing             │ - Performance Testing              │
│ - Integration Testing      │ - Load Testing                     │
│ - System Testing           │ - Stress Testing                   │
│ - Acceptance Testing       │ - Security Testing                 │
│ - Smoke Testing            │ - Usability Testing                │
│ - Sanity Testing           │ - Compatibility Testing            │
│ - Regression Testing       │ - Reliability Testing              │
│ - Exploratory Testing      │ - Scalability Testing              │
└────────────────────────────┴────────────────────────────────────┘
```

---

## Detailed Testing Types

### Smoke Testing

**Purpose:** Verify basic functionality works after a new build.

| Aspect | Details |
|--------|---------|
| **Also Called** | Build Verification Testing (BVT) |
| **Scope** | Critical functionalities only |
| **Depth** | Shallow - broad coverage |
| **When** | After every new build |

---

### Sanity Testing

**Purpose:** Verify specific functionality after minor changes.

| Aspect | Details |
|--------|---------|
| **Scope** | Specific modules affected by changes |
| **Depth** | Deep - narrow coverage |
| **When** | After bug fixes or minor changes |

---

### Regression Testing

**Purpose:** Ensure existing functionality is not broken by new changes.

| Aspect | Details |
|--------|---------|
| **Scope** | Previously working features |
| **When** | After any code change |
| **Best Practice** | Automate regression tests |

```
┌─────────────────────────────────────────────────┐
│          REGRESSION TESTING SCENARIOS           │
├─────────────────────────────────────────────────┤
│                                                 │
│  When to Perform:                               │
│  ┌─────────────────────────────────────────┐   │
│  │ - New feature added                      │   │
│  │ - Bug fix deployed                       │   │
│  │ - Configuration changes                  │   │
│  │ - Patch updates                          │   │
│  │ - Environment changes                    │   │
│  └─────────────────────────────────────────┘   │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

### Exploratory Testing

**Purpose:** Simultaneous learning, test design, and execution.

| Aspect | Details |
|--------|---------|
| **Approach** | Unscripted, investigative |
| **Best For** | Finding unexpected issues |
| **Skill Required** | Experience and domain knowledge |

---

### Performance Testing

```
┌─────────────────────────────────────────────────────────────────┐
│                PERFORMANCE TESTING TYPES                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐       │
│   │    LOAD      │   │   STRESS     │   │   SPIKE      │       │
│   │   TESTING    │   │   TESTING    │   │   TESTING    │       │
│   ├──────────────┤   ├──────────────┤   ├──────────────┤       │
│   │ Normal load  │   │ Beyond normal│   │ Sudden load  │       │
│   │ conditions   │   │ capacity     │   │ increase     │       │
│   └──────────────┘   └──────────────┘   └──────────────┘       │
│                                                                 │
│   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐       │
│   │  ENDURANCE   │   │  VOLUME      │   │ SCALABILITY  │       │
│   │   TESTING    │   │   TESTING    │   │   TESTING    │       │
│   ├──────────────┤   ├──────────────┤   ├──────────────┤       │
│   │ Extended     │   │ Large data   │   │ Increasing   │       │
│   │ period test  │   │ volumes      │   │ resources    │       │
│   └──────────────┘   └──────────────┘   └──────────────┘       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

| Type | Purpose | Example |
|------|---------|---------|
| **Load** | Test under expected load | 1000 concurrent users |
| **Stress** | Test beyond capacity | 5000 users (limit: 2000) |
| **Spike** | Test sudden load spikes | 0 to 5000 users instantly |
| **Endurance** | Test over extended time | 1000 users for 24 hours |
| **Volume** | Test with large data | 1 million records |
| **Scalability** | Test scaling capability | Add servers under load |

---

### Security Testing

**Purpose:** Identify vulnerabilities and security risks.

| Type | Description |
|------|-------------|
| **Vulnerability Scanning** | Automated scanning for known vulnerabilities |
| **Penetration Testing** | Simulated attacks to find weaknesses |
| **Security Auditing** | Code and configuration review |
| **Ethical Hacking** | Authorized attempt to breach security |

### OWASP Top 10 Testing Areas
1. Injection
2. Broken Authentication
3. Sensitive Data Exposure
4. XML External Entities
5. Broken Access Control
6. Security Misconfiguration
7. Cross-Site Scripting (XSS)
8. Insecure Deserialization
9. Using Components with Known Vulnerabilities
10. Insufficient Logging and Monitoring

---

### Usability Testing

**Purpose:** Evaluate user experience and interface intuitiveness.

| Aspect | Focus Areas |
|--------|-------------|
| **Learnability** | How easy to learn for new users |
| **Efficiency** | How quickly tasks can be completed |
| **Memorability** | How easy to remember for returning users |
| **Errors** | How many errors users make |
| **Satisfaction** | How pleasant to use |

---

### Compatibility Testing

**Purpose:** Verify software works across different environments.

| Type | Testing Focus |
|------|--------------|
| **Browser** | Chrome, Firefox, Safari, Edge |
| **OS** | Windows, macOS, Linux, iOS, Android |
| **Device** | Desktop, Tablet, Mobile |
| **Network** | Different bandwidth conditions |
| **Database** | Different database versions |

---

## Testing Techniques

### Black Box Testing
- Test based on requirements without knowing internal code
- **Techniques:** Equivalence Partitioning, Boundary Value Analysis, Decision Table

### White Box Testing
- Test based on internal code structure
- **Techniques:** Statement Coverage, Branch Coverage, Path Coverage

### Grey Box Testing
- Combination of black box and white box
- Partial knowledge of internal structure

```
┌─────────────────────────────────────────────────────────────────┐
│              TESTING TECHNIQUES COMPARISON                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   BLACK BOX          GREY BOX           WHITE BOX              │
│   ┌────────┐        ┌────────┐         ┌────────┐              │
│   │ ###### │        │ ..#### │         │ ...... │              │
│   │ ###### │        │ ..#### │         │ ...... │              │
│   │ ###### │        │ ..#### │         │ ...... │              │
│   └────────┘        └────────┘         └────────┘              │
│   No knowledge      Partial            Full                    │
│   of internals      knowledge          knowledge               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Quick Reference Table

| Testing Type | Focus | When | Who |
|--------------|-------|------|-----|
| Unit | Individual components | Development | Developers |
| Integration | Module interactions | After unit tests | Dev/QA |
| System | Complete system | After integration | QA Team |
| Acceptance | Business requirements | Before release | Users/BA |
| Smoke | Build stability | Every build | QA Team |
| Sanity | Specific changes | After fixes | QA Team |
| Regression | Existing features | After changes | QA Team |
| Performance | Speed and stability | Before release | Performance Team |
| Security | Vulnerabilities | Before release | Security Team |
| Usability | User experience | During development | UX Team |
