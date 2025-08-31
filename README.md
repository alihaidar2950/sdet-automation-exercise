# Automation Exercise Test Automation Project

This repository contains an end-to-end test automation framework built with **Playwright + TypeScript** for the demo website [Automation Exercise](https://automationexercise.com).  
The goal is to showcase professional-grade test planning, implementation, and reporting practices that align with real-world SDET roles.

---

## 📌 Project Objectives

- Demonstrate **Playwright** and **TypeScript** skills for functional, integration, and end-to-end testing.
- Implement a **structured test plan** covering test strategy, scope, tools, risks, and execution.
- Provide **scalable test cases** with clear labeling by test type (functional, integration, regression, etc.).
- Integrate **best practices** like Page Object Model (POM), reusable utilities, and test reporting.

---

## 🛠️ Tech Stack

- **Programming Language**: TypeScript  
- **Test Framework**: Playwright Test Runner  
- **Assertions**: Playwright’s built-in `expect` API  
- **Reporting**: Playwright HTML reporter (optionally Allure for extended reporting)  
- **Version Control**: GitHub  
- **CI/CD (optional later)**: GitHub Actions  

---

## 📂 Repository Structure

```plaintext
automation-exercise-tests/
├── test-plan/                 # Detailed test plan documents
│   └── Automation_Exercise_Test_Plan.md
├── tests/                     # Automated test cases
│   ├── auth/                  # Login, Signup, Logout
│   ├── cart/                  # Add/remove items, checkout
│   ├── products/              # Product search, filtering
│   └── regression/            # End-to-end regression suites
├── pages/                     # Page Object Models
├── utils/                     # Reusable helper functions
├── playwright.config.ts       # Playwright configuration
├── package.json               # Dependencies
├── tsconfig.json              # TypeScript configuration
└── README.md                  # Project overview (this file)
