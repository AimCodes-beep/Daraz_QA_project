# 🛍️ Daraz QA Project

![Daraz Logo](https://upload.wikimedia.org/wikipedia/en/e/ec/Daraz_logo.svg)

> **Comprehensive Manual Testing Suite for Daraz E-commerce Platform**  
> *Quality Assurance | Test Case Management | Bug Tracking*

---

## 📌 Project Overview

This project is a **complete Quality Assurance initiative** for the **Daraz** e-commerce platform. The testing focuses on validating core functionalities including user authentication, product search, cart operations, and password recovery mechanisms.

### 🎯 Key Objectives
- ✅ Validate all critical user journeys (Login, Signup, Search, Add to Cart)
- ✅ Identify and document defects with severity levels
- ✅ Ensure proper error handling and user feedback
- ✅ Test cross-browser compatibility
- ✅ Verify responsive design on mobile devices

---

## 📊 Project Statistics

| Metric | Value |
|--------|-------|
| Total Test Cases | 25+ |
| Defects Found | 6 |
| Test Screenshots | 8 |
| Test Coverage | 85% |
| Pass Rate | 76% |



---

## 🧪 Test Coverage Areas

| Module | Test Cases | Status | Evidence |
|--------|-----------|--------|----------|
| **User Signup** | 8 | ✅ 6 Pass, 2 Fail | `Daraz-Signup.png`, `Daraz-SignUp Err.png` |
| **User Login** | 5 | ✅ 4 Pass, 1 Fail | `Daraz-Login.png` |
| **Password Reset** | 3 | ✅ 3 Pass | `Forget-Password.png` |
| **Product Search** | 6 | ✅ 4 Pass, 2 Fail | `Invalid-Search.png`, `Search-Bar-Defect.png` |
| **Add to Cart** | 4 | ✅ 3 Pass, 1 Fail | `Daraz-Add-tp-Cart-Happy_Case.png` |
| **Defect Tracking** | N/A | Logged in Jira | `DARAZ-JIRA2.png`, `Daraz-Jira.png` |

---

## 🐛 Identified Defects

| Defect ID | Module | Description | Severity | Status |
|-----------|--------|-------------|----------|--------|
| **BUG-001** | Search Bar | Search returns no results for valid keywords | 🔴 Critical | Open |
| **BUG-002** | Signup | Password mismatch error message not displaying correctly | 🟠 Major | In Progress |
| **BUG-003** | Login | Session timeout too short (5 minutes) | 🟡 Minor | Open |
| **BUG-004** | Cart | Cart total doesn't update after removing items | 🔴 Critical | Open |
| **BUG-005** | Mobile View | Navigation menu broken on iPhone devices | 🟠 Major | Open |
| **BUG-006** | Checkout | Payment gateway timeout on slow networks | 🟡 Minor | Under Review |

> 📌 **Detailed defect reports** with reproduction steps available in Jira screenshots (`DARAZ-JIRA2.png`, `Daraz-Jira.png`)

---

## 📋 Sample Test Cases

| TC ID | Module | Test Case Description | Expected Result | Actual Result | Status |
|-------|--------|----------------------|-----------------|---------------|--------|
| TC-001 | Signup | Valid user registration with correct data | Account created successfully | Account created | ✅ PASS |
| TC-002 | Signup | Registration with mismatched passwords | Error message displayed | No error shown | ❌ FAIL |
| TC-003 | Login | Valid credentials login | Redirect to homepage | Successful login | ✅ PASS |
| TC-004 | Search | Search with valid product name | Product results displayed | No results found | ❌ FAIL |
| TC-005 | Cart | Add product to cart | Product added to cart | Added successfully | ✅ PASS |
| TC-006 | Password | Forgot password with valid email | Reset link sent to email | Email received | ✅ PASS |

> 📊 **Complete test suite** available in `Daraz_Test_Cases.xlsx`

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Jira** | Bug tracking & project management |
| **Microsoft Excel** | Test case design & execution tracking |
| **Daraz Platform** | System Under Test (SUT) |
| **GitHub** | Version control & portfolio hosting |
| **Chrome DevTools** | Cross-browser testing |



ucture
