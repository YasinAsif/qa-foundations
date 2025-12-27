# Software Testing Life Cycle (STLC)

## Overview

The Software Testing Life Cycle (STLC) is a sequence of specific activities conducted during the testing process to ensure software quality goals are met. It defines the steps for validating and verifying software quality.

## STLC Flow Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     SOFTWARE TESTING LIFE CYCLE (STLC)                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────┐                                                        │
│  │   Requirement   │ <-- Entry: Requirements Documents                      │
│  │    Analysis     │ --> Exit: RTM, Automation Feasibility Report           │
│  └────────┬────────┘                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  ┌─────────────────┐                                                        │
│  │  Test Planning  │ <-- Entry: Requirements, RTM                           │
│  │                 │ --> Exit: Test Plan, Effort Estimation                 │
│  └────────┬────────┘                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  ┌─────────────────┐                                                        │
│  │   Test Case     │ <-- Entry: Requirements, Test Plan                     │
│  │  Development    │ --> Exit: Test Cases, Test Data, Scripts               │
│  └────────┬────────┘                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  ┌─────────────────┐                                                        │
│  │  Environment    │ <-- Entry: System Design, Env Setup Plan               │
│  │     Setup       │ --> Exit: Environment Ready, Smoke Test Results        │
│  └────────┬────────┘                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  ┌─────────────────┐                                                        │
│  │ Test Execution  │ <-- Entry: Test Cases, Test Data, Environment          │
│  │                 │ --> Exit: Test Results, Defect Reports                 │
│  └────────┬────────┘                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  ┌─────────────────┐                                                        │
│  │  Test Cycle     │ <-- Entry: Test Results, Defect Logs                   │
│  │    Closure      │ --> Exit: Test Closure Report, Metrics                 │
│  └─────────────────┘                                                        │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Phase 1: Requirement Analysis

### Objective
Understand and analyze the testing requirements.

### Activities
| Activity | Description |
|----------|-------------|
| Requirement Review | Analyze functional and non-functional requirements |
| Identify Testable Requirements | Determine what can be tested |
| Clarify Ambiguities | Resolve unclear requirements with stakeholders |
| Prioritize Requirements | Rank requirements by importance |

### Entry Criteria
- Requirements Document (SRS)
- Application architecture documents
- Acceptance criteria

### Exit Criteria
- Requirements Traceability Matrix (RTM)
- Automation feasibility report
- Clarified requirements

### Deliverables
- Requirement Traceability Matrix (RTM)
- Automation Feasibility Report
- List of Testable Requirements

---

## Phase 2: Test Planning

### Objective
Define the test strategy and plan for the project.

### Activities
| Activity | Description |
|----------|-------------|
| Define Test Strategy | Determine testing approach |
| Estimate Effort | Calculate time and resources needed |
| Identify Risks | Document potential risks and mitigations |
| Define Scope | Determine what will and won't be tested |
| Tool Selection | Choose testing tools |

### Entry Criteria
- Requirements Documents
- RTM
- Automation Feasibility Report

### Exit Criteria
- Approved Test Plan
- Effort Estimation Document
- Resource Planning

### Deliverables
- Test Plan Document
- Effort Estimation
- Resource Plan
- Test Schedule

### Test Plan Components
```
┌─────────────────────────────────────┐
│          TEST PLAN                  │
├─────────────────────────────────────┤
│ 1. Test Objectives                  │
│ 2. Test Scope (In/Out)              │
│ 3. Test Strategy                    │
│ 4. Test Environment                 │
│ 5. Entry/Exit Criteria              │
│ 6. Test Deliverables                │
│ 7. Roles and Responsibilities       │
│ 8. Risk Analysis                    │
│ 9. Schedule and Milestones          │
│ 10. Tools and Resources             │
└─────────────────────────────────────┘
```

---

## Phase 3: Test Case Development

### Objective
Create detailed test cases and prepare test data.

### Activities
| Activity | Description |
|----------|-------------|
| Write Test Cases | Create detailed test scenarios |
| Create Test Data | Prepare data for test execution |
| Review Test Cases | Peer review for quality |
| Develop Automation Scripts | Create automated test scripts |
| Update RTM | Map test cases to requirements |

### Entry Criteria
- Requirements Document
- Approved Test Plan
- RTM

### Exit Criteria
- Reviewed Test Cases
- Approved Test Scripts
- Test Data Ready

### Deliverables
- Test Cases
- Test Data
- Automation Scripts
- Updated RTM

### Test Case Template
```
┌─────────────────────────────────────────────────────────┐
│ Test Case ID: TC_LOGIN_001                              │
├─────────────────────────────────────────────────────────┤
│ Title: Verify successful login with valid credentials   │
│ Priority: High                                          │
│ Module: Authentication                                  │
├─────────────────────────────────────────────────────────┤
│ Preconditions:                                          │
│ - User account exists                                   │
│ - User is on login page                                 │
├─────────────────────────────────────────────────────────┤
│ Test Steps:                                             │
│ 1. Enter valid username                                 │
│ 2. Enter valid password                                 │
│ 3. Click Login button                                   │
├─────────────────────────────────────────────────────────┤
│ Expected Result:                                        │
│ User is logged in and redirected to dashboard           │
└─────────────────────────────────────────────────────────┘
```

---

## Phase 4: Test Environment Setup

### Objective
Prepare the hardware and software environment for testing.

### Activities
| Activity | Description |
|----------|-------------|
| Environment Setup | Configure test servers and databases |
| Install Software | Set up required applications |
| Configure Network | Set up network connections |
| Smoke Testing | Verify environment readiness |
| Document Setup | Create environment documentation |

### Entry Criteria
- System Design Documents
- Environment Setup Plan
- Required Hardware/Software

### Exit Criteria
- Environment ready for testing
- Smoke test passed
- Access permissions granted

### Deliverables
- Environment Ready
- Smoke Test Results
- Environment Documentation

---

## Phase 5: Test Execution

### Objective
Execute test cases and report defects.

### Activities
| Activity | Description |
|----------|-------------|
| Execute Test Cases | Run tests as per plan |
| Log Defects | Report bugs in tracking tool |
| Map Defects to Test Cases | Link bugs to test cases |
| Re-test Fixed Defects | Verify bug fixes |
| Regression Testing | Ensure no new issues |

### Entry Criteria
- Test Cases approved
- Test Environment ready
- Test Data available
- Build deployed

### Exit Criteria
- All test cases executed
- Defects logged and tracked
- Test summary report created

### Deliverables
- Test Execution Results
- Defect Reports
- Updated RTM
- Daily Status Reports

### Defect Life Cycle
```
┌───────┐    ┌────────┐    ┌──────────┐    ┌────────┐
│  New  │───►│Assigned│───►│   Open   │───►│ Fixed  │
└───────┘    └────────┘    └──────────┘    └────────┘
                                │               │
                                ▼               ▼
                          ┌──────────┐    ┌──────────┐
                          │ Rejected │    │ Retest   │
                          └──────────┘    └────┬─────┘
                                               │
                          ┌──────────┐         │
                          │ Reopened │◄────────┤
                          └──────────┘         │
                                               ▼
                                         ┌──────────┐
                                         │  Closed  │
                                         └──────────┘
```

---

## Phase 6: Test Cycle Closure

### Objective
Conclude testing activities and document learnings.

### Activities
| Activity | Description |
|----------|-------------|
| Evaluate Completion | Check exit criteria met |
| Document Learnings | Capture lessons learned |
| Create Test Metrics | Calculate quality metrics |
| Archive Test Artifacts | Store documents for future |
| Sign-off | Get stakeholder approval |

### Entry Criteria
- Test execution complete
- All critical defects resolved
- Exit criteria achieved

### Exit Criteria
- Test Closure Report approved
- Metrics published
- Artifacts archived

### Deliverables
- Test Closure Report
- Test Metrics
- Lessons Learned Document

---

## STLC vs SDLC Mapping

```
┌─────────────────────────────────────────────────────────────┐
│           SDLC                    STLC                      │
├─────────────────────────────────────────────────────────────┤
│  Requirements     <-------->   Requirement Analysis         │
│  Design           <-------->   Test Planning                │
│  Development      <-------->   Test Case Development        │
│  Testing          <-------->   Test Execution               │
│  Deployment       <-------->   Test Cycle Closure           │
│  Maintenance      <-------->   Regression Testing           │
└─────────────────────────────────────────────────────────────┘
```

---

## Key Metrics

| Metric | Formula |
|--------|---------|
| **Test Case Execution Rate** | (Executed Tests / Total Tests) x 100 |
| **Pass Rate** | (Passed Tests / Executed Tests) x 100 |
| **Defect Density** | Defects / Size (KLOC or FP) |
| **Defect Leakage** | (Defects in Production / Total Defects) x 100 |
| **Test Coverage** | (Requirements Covered / Total Requirements) x 100 |
