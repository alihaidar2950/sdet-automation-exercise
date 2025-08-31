# 🧪 Automation Exercise – Test Plan

## 1. Introduction

This document defines the **test strategy, scope, tools, and execution plan** for automating the website [Automation Exercise](https://automationexercise.com).  
The objective is to demonstrate a professional-grade approach to automated testing using Playwright + TypeScript.

---

## 2. Scope

### In-Scope

- **Functional Testing** → Core features like login, signup, product search, add to cart, checkout.
- **Integration Testing** → Verify interactions between modules (e.g., product search + cart flow).
- **Regression Testing** → Ensure previously working features remain stable after updates.
- **End-to-End Testing** → Simulate complete user journeys.

### Out-of-Scope

- Performance & load testing (not cost-effective for this portfolio project).
- Security testing (not feasible on third-party demo site).
- Unit testing (not relevant — no access to source code).

---

## 3. Test Types

| Test Type           | Example Scenarios                                                                 |
|----------------------|-----------------------------------------------------------------------------------|
| **Functional**      | Verify login with valid/invalid data, verify cart updates correctly.              |
| **Integration**     | Search product → add to cart → proceed to checkout.                               |
| **Regression**      | Re-run all functional tests after UI updates.                                     |
| **End-to-End (E2E)**| Full purchase flow: Signup → Login → Browse → Add to Cart → Checkout.             |
| **Smoke**           | Minimal suite: homepage loads, login works, product search works.                 |
| **Exploratory**     | Ad-hoc manual + automated checks for unexpected behaviors.                        |

---

## 4. Tools & Tech Stack

- **Playwright Test Runner** (TypeScript) → Core automation
- **Page Object Model (POM)** → Maintainable test structure
- **Assertions**: Playwright `expect` API
- **Reports**: Playwright HTML Reporter (optionally Allure)
- **CI/CD**: GitHub Actions (to be added later)

---

## 5. Test Environment

- **Target Site**: [Automation Exercise](https://automationexercise.com)
- **Browsers**: Chromium, Firefox, WebKit
- **Test Data**:  
  - Dummy email accounts for signup  
  - Static product IDs from site catalog  

---

## 6. Test Execution Strategy

1. Smoke tests run on every commit.  
2. Functional + integration suites run nightly.  
3. Full regression suite runs weekly or before major release demos.  
4. Reports are automatically generated and published via GitHub Actions (planned).  

---

## 7. Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Site downtime | Blocks test execution | Re-run later; add retries |
| Site data reset | Invalidates test data | Use dynamic test data generators |
| Rate limiting | Possible test failures | Add throttling / retries |

---

## 8. Deliverables

- **Automated Test Scripts** (Playwright + TypeScript)
- **Test Plan** (this document)
- **Test Reports** (HTML/Allure)
- **GitHub Repo** (for portfolio presentation)

---

## 9. References

- [Playwright Docs](https://playwright.dev/)  
- [Automation Exercise Website](https://automationexercise.com)  

---
