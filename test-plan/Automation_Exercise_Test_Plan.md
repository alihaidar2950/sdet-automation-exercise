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

## 10. Test Cases

### 10.1 UI Test Cases

| ID    | Title                                         | Steps                                                                                         | Expected Result                                  |
|-------|-----------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| TC01  | Login with valid credentials                  | 1. Go to login page  2. Enter valid email/password  3. Click login                            | User is logged in and redirected to dashboard    |
| TC02  | Login with invalid credentials                | 1. Go to login page  2. Enter invalid email/password  3. Click login                          | Error message is displayed                       |
| TC03  | Signup with new user                          | 1. Go to signup  2. Enter new user details  3. Submit form                                    | Account is created and user is logged in         |
| TC04  | Signup with existing email                    | 1. Go to signup  2. Enter existing email  3. Submit form                                      | Error message about duplicate email              |
| TC05  | Search for a product                          | 1. Enter product name in search  2. Click search                                              | Relevant products are displayed                  |
| TC06  | Add product to cart                           | 1. Search/select product  2. Click 'Add to Cart'                                              | Product appears in cart                          |
| TC07  | Remove product from cart                      | 1. Add product to cart  2. Go to cart  3. Remove product                                      | Product is removed from cart                     |
| TC08  | Checkout as registered user                   | 1. Login  2. Add product to cart  3. Checkout  4. Complete purchase                           | Order confirmation is shown                      |
| TC09  | Checkout as guest                             | 1. Add product to cart  2. Checkout as guest  3. Enter details  4. Complete purchase          | Order confirmation is shown                      |
| TC10  | Homepage loads                                | 1. Navigate to homepage                                                                       | Homepage content is visible                      |
| TC11  | Login page loads                              | 1. Navigate to login page                                                                     | Login form is visible                            |
| TC12  | Product search basic                          | 1. Enter product name  2. Click search                                                        | Product list is updated                          |
| TC13  | Validate cart persists after login            | 1. Add product to cart as guest  2. Login  3. Check cart                                      | Cart still contains product                      |
| TC14  | Logout                                        | 1. Login  2. Click logout                                                                     | User is logged out and redirected to homepage    |
| TC15  | Password reset                                | 1. Go to login  2. Click 'Forgot Password'  3. Enter email  4. Submit                         | Password reset email sent                        |
| TC16  | Pagination on product listing                 | 1. Go to product listing  2. Navigate to next page                                            | Next set of products displayed                   |
| TC17  | Filter products by category                   | 1. Select category filter  2. View products                                                   | Only products from selected category shown       |
| TC18  | Add/remove multiple products in cart          | 1. Add several products  2. Remove some  3. Check cart                                        | Cart updates correctly                           |
| TC19  | Checkout with empty cart                      | 1. Go to cart  2. Remove all items  3. Try to checkout                                        | Checkout is blocked or warning shown             |
| TC20  | Responsive layout (mobile)                    | 1. Open site on mobile viewport                                                               | Layout adapts, navigation works                  |
| TC21  | Error handling for network failure            | 1. Simulate network loss  2. Try to load page                                                 | User sees error message                          |
| TC22  | Wishlist add/remove                           | 1. Add product to wishlist  2. Remove product from wishlist                                   | Wishlist updates correctly                       |
| TC23  | View order history                            | 1. Login  2. Go to order history page                                                         | Past orders are listed                           |
| TC24  | Update account profile                        | 1. Login  2. Go to profile  3. Edit details  4. Save                                          | Profile updates are saved                        |
| TC25  | Newsletter subscription                       | 1. Enter email in newsletter box  2. Submit                                                   | Confirmation message shown                       |
| TC26  | Contact form submission                       | 1. Fill contact form  2. Submit                                                               | Success message shown                            |
| TC27  | Social media links                            | 1. Click each social media link in footer                                                     | Correct social page opens in new tab             |
| TC28  | Product image zoom                            | 1. Hover/click product image                                                                  | Image zooms or modal opens                       |
| TC29  | Breadcrumb navigation                         | 1. Navigate to product  2. Use breadcrumb links                                               | User is taken to correct category/page           |
| TC30  | Cart icon updates                             | 1. Add/remove products from cart                                                              | Cart icon count updates in header                |
| TC31  | Language switcher                             | 1. Change site language (if available)                                                        | Site content updates to selected language        |
| TC32  | Accessibility - tab navigation                | 1. Use Tab key to navigate                                                                    | All interactive elements are reachable           |
| TC33  | Accessibility - screen reader labels          | 1. Inspect elements with screen reader                                                        | Labels and roles are present                     |
| TC34  | Session timeout                               | 1. Login  2. Wait for session timeout                                                         | User is logged out and prompted to login again   |
| TC35  | Add review to product                         | 1. Login  2. Go to product  3. Submit review                                                  | Review is added and visible                      |
| TC36  | Filter products by price                      | 1. Set price filter  2. View products                                                         | Only products in price range shown               |
| TC37  | Sorting products                              | 1. Change sort order (e.g., price low-high)                                                   | Products are sorted accordingly                  |

### 10.2 API Test Cases

| ID    | Title                                         | Steps                                                                                         | Expected Result                                  |
|-------|-----------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| TC38  | Get all products                              | 1. Send GET request to /api/products                                                          | 200 OK, product list returned                    |
| TC39  | Create new user                               | 1. Send POST request to /api/users with valid data                                            | 201 Created, user object returned                |
| TC40  | Login user                                    | 1. Send POST request to /api/login with valid credentials                                     | 200 OK, token returned                           |
| TC41  | Add product to cart                           | 1. Send POST request to /api/cart with product ID                                             | 200 OK, cart updated                             |
| TC42  | Delete user                                   | 1. Send DELETE request to /api/users/{id}                                                     | 200 OK, user deleted                             |
| TC43  | Update user profile                           | 1. Send PUT request to /api/users/{id} with new data                                          | 200 OK, updated user returned                    |
| TC44  | Get order history                             | 1. Send GET request to /api/orders as logged-in user                                          | 200 OK, order list returned                      |
| TC45  | Add product review                            | 1. Send POST request to /api/products/{id}/reviews                                            | 201 Created, review object returned              |

### 10.3 Integration Test Cases

| ID    | Title                                         | Steps                                                                                         | Expected Result                                  |
|-------|-----------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| TC46  | Product search to checkout flow               | 1. Search product  2. Add to cart  3. Checkout                                                | Order is placed successfully                     |
| TC47  | Signup and purchase in one session            | 1. Signup  2. Add product to cart  3. Checkout                                                | Order is placed and user is logged in            |

### 10.4 Smoke Test Cases

| ID    | Title                                         | Steps                                                                                         | Expected Result                                  |
|-------|-----------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| TC48  | Homepage loads                                | 1. Navigate to homepage                                                                       | Homepage content is visible                      |
| TC49  | Login page loads                              | 1. Navigate to login page                                                                     | Login form is visible                            |
| TC50  | Product search basic                          | 1. Enter product name  2. Click search                                                        | Product list is updated                          |

### 10.5 Exploratory Test Cases

| ID    | Title                                         | Steps                                                                                         | Expected Result                                  |
|-------|-----------------------------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| TC51  | Unexpected popup handling                     | 1. Trigger unexpected popup (if any)                                                          | Test can handle/dismiss popup                    |
