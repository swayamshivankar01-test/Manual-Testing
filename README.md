# E-Commerce Manual Testing Project

A manual QA project for a sample e-commerce web application. It covers the full testing documentation flow: requirements → test scenarios → detailed test cases → defect reporting.

The work is split into two feature areas, each with its own requirement document and scenario sheet:

| Area | Features covered |
|------|------------------|
| **Account & Catalog** | Registration, Login, Product Search & Display |
| **Purchase Flow** | Add to Cart, Cart Management, Checkout, Payment |

---

## Repository Structure

```
.
├── E-Commerce_Requirement_Document_bugasura.docx   # SRS – Registration, Login, Search
├── E-Commerce_Test_Scenarios_bugasura.xlsx         # 8 scenarios (TS-01 … TS-08)
│
├── Ecommerce_Requirement_Document_chatGPT.docx     # Requirements – Cart, Checkout, Payment
├── Ecommerce_Test_Scenarios_chatGPT.xlsx           # 13 scenarios (TS_01 … TS_13)
├── Ecom_test_cases_ChatGPT.xlsx                    # 17 detailed test cases (TC_001 … TC_017)
│
└── checkout_bug_report.docx                        # Sample defect report (card number validation)
```

---

## Documents

### 1. Requirement Documents
- **`E-Commerce_Requirement_Document_bugasura.docx`** – Software Requirement Specification (SRS) dated 09 Mar 2026.
  - Functional requirements **FR-1 – FR-7**: registration, login, error handling, product search, product details, filter/sort.
  - Non-functional requirements **NFR-1 – NFR-5**: page load under 3 s, responsive design, Chrome/Firefox/Edge support, encrypted data transmission, 99% availability.
  - Admin functionality is out of scope.
- **`Ecommerce_Requirement_Document_chatGPT.docx`** – Requirement document dated 09 Mar 2026.
  - Functional requirements **FR-01 – FR-08**: add to cart, update/remove items, price calculation, shipping details, checkout validation, payment method selection, order confirmation.
  - Non-functional requirements **NFR-01 – NFR-04**: load time, browser support, responsiveness, secure payment processing.

### 2. Test Scenarios
- **`E-Commerce_Test_Scenarios_bugasura.xlsx`** – 8 high-level scenarios across Registration, Login and Product Search & Display (valid/invalid data, keyword search, no-results, product details, sort by price).
- **`Ecommerce_Test_Scenarios_chatGPT.xlsx`** – 13 scenarios across Add to Cart, Cart Management, Checkout and Payment.

### 3. Test Cases
- **`Ecom_test_cases_ChatGPT.xlsx`** – 17 detailed test cases (`TC_001` – `TC_017`) with these columns:
  `Test Case ID` · `Test Case Objective` · `Preconditions` · `Test Steps` · `Input Data` · `Expected Result`

  | Range | Focus |
  |-------|-------|
  | TC_001 – TC_002 | Add to cart from Product Listing Page / Product Details Page |
  | TC_003 – TC_004 | Multiple line items and subtotal calculation |
  | TC_005 – TC_009 | Quantity increase/decrease, remove item, empty cart, line total |
  | TC_010 | Cart persistence after refresh |
  | TC_011 – TC_014 | Proceed to checkout, mandatory shipping field validation, order summary |
  | TC_015 – TC_017 | Payment method selection, successful payment/order confirmation, invalid payment handling |

### 4. Defect Report
- **`checkout_bug_report.docx`** – Checkout page validation issue.
  - **Summary:** The Card Number field accepts invalid or excessively long values (e.g. `123456789012345678901234567890`) and the order is placed without any error.
  - **Expected:** Card number format and length are validated, with an error message on invalid input.
  - **Severity / Priority:** Medium / Medium.

---

## Traceability Overview

```
Requirement (FR/NFR)  →  Test Scenario (TS)  →  Test Case (TC)  →  Bug Report
```

| Requirement | Scenarios | Test Cases |
|-------------|-----------|------------|
| FR-01 Add to cart | TS_01, TS_02 | TC_001 – TC_004 |
| FR-02 / FR-03 Update / remove | TS_03, TS_04, TS_06 | TC_005 – TC_010 |
| FR-04 Total price | TS_05 | TC_004, TC_009 |
| FR-05 / FR-06 Shipping & validation | TS_07, TS_08 | TC_011 – TC_013 |
| FR-07 Payment method | TS_10 | TC_015 |
| FR-08 Order confirmation | TS_09, TS_11, TS_13 | TC_014, TC_016 |
| Invalid payment handling | TS_12 | TC_017 → *checkout bug report* |

> Registration, Login and Search scenarios (TS-01 – TS-08 in the Bugasura sheet) are defined but do not yet have detailed test cases.

---

## Testing Scope

- **Type:** Manual functional testing (black-box)
- **Browsers:** Chrome, Firefox, Edge
- **Devices:** Desktop and mobile (responsive)
- **Out of scope:** Admin functionality, automation, performance/load testing

## How to Use

1. Read the requirement documents to understand expected behaviour.
2. Pick scenarios from the scenario sheets for the feature under test.
3. Execute the matching test cases step by step in the target browser.
4. Record actual vs. expected results; log any deviation as a defect using the format in `checkout_bug_report.docx` (Steps to Reproduce, Actual Result, Expected Result, Severity & Priority).

## Suggested Next Steps

- Write detailed test cases for Registration, Login and Product Search.
- Add an execution-status column (Pass / Fail / Blocked) and actual results to the test case sheet.
- Add a requirements traceability matrix (RTM) as a spreadsheet.
- Cover the non-functional requirements (load time, browser/device compatibility, security).

## Repository

Source: <https://github.com/swayamshivankar01-test/Manual-Testing>
