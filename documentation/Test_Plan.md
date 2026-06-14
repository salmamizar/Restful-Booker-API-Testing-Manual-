# Test Plan - Restful Booker API Manual Testing

## 1. Project Overview

This project covers manual API testing for the Restful Booker API. The purpose is to validate the main API functionalities, including authentication, booking creation, booking retrieval, filtering, full update, partial update, deletion, and end-to-end booking lifecycle.

## 2. Application Under Test

**Application Name:** Restful Booker API  
**Base URL:** `https://restful-booker.herokuapp.com`  
**API Type:** REST API  
**Data Format:** JSON  
**Authentication:** Token-based authentication using cookie token

## 3. Testing Objective

The objective of this project is to verify that the Restful Booker API behaves correctly according to expected API behavior, validates request data properly, protects restricted endpoints with authentication, and returns correct status codes and response bodies.

## 4. Scope of Testing

The following modules are included in scope:

- Authentication
- Create Booking
- Get Booking
- Filter Booking
- Full Update Booking using PUT
- Partial Update Booking using PATCH
- Delete Booking
- End-to-End Booking Lifecycle

## 5. Out of Scope

The following items are out of scope for this manual testing phase:

- UI Testing
- Database Testing
- Advanced Security Testing
- Load Testing
- Advanced Performance Testing
- Automation Testing
- CI/CD Pipeline Integration

## 6. Test Types Covered

- Functional API Testing
- Positive Testing
- Negative Testing
- Boundary Value Testing
- Data Type Validation
- Header Validation
- Authentication and Authorization Testing
- End-to-End API Testing
- Basic Response Time Check

## 7. Tools Used

- Postman
- Microsoft Excel / Google Sheets
- GitHub
- Markdown Documentation

## 8. Test Environment

| Item | Value |
|---|---|
| Base URL | `https://restful-booker.herokuapp.com` |
| Content-Type | `application/json` |
| Accept | `application/json` |
| Auth Type | Cookie token |
| Environment Variables | `token`, `bookingId`, `firstname`, `lastname`, `checkin`, `checkout` |

## 9. Entry Criteria

Testing can start when:

- API is accessible
- Postman is installed and ready
- Valid authentication credentials are available
- Test cases are prepared and reviewed
- Test data is prepared
- Postman environment variables are configured

## 10. Exit Criteria

Testing is considered complete when:

- All high-priority test cases are executed
- End-to-end flow is executed successfully
- Failed test cases are analyzed
- Defects or API observations are documented
- Postman collection and environment are exported

## 11. Test Data

Main valid booking payload:

```json
{
  "firstname": "Mervat",
  "lastname": "Ahmed",
  "totalprice": 250,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-07-01",
    "checkout": "2026-07-05"
  },
  "additionalneeds": "Breakfast"
}
```

Valid credentials:

```json
{
  "username": "admin",
  "password": "password123"
}
```

## 12. Test Deliverables

- Test Plan
- Test Cases
- End-to-End Scenarios
- Postman Collection
- Postman Environment
- GitHub Repository

## 13. Risks and Assumptions

| Risk / Assumption | Impact |
|---|---|
| Public API may be unstable | Some tests may fail due to availability issues |
| Some invalid requests may return 500 instead of 400 | Actual behavior should be documented as an observation or defect |
| Test data may be deleted or changed | New booking data should be created during execution |
| API behavior may differ from standard REST conventions | Known deviations should be documented |

## 14. Known API Behaviors to Document

- Invalid authentication may return status code 200 with `reason: Bad credentials`.
- Delete booking may return 201 instead of the common REST status 204.
- Missing required fields may return 500 instead of 400.
- Some validation rules may not be enforced by the API.

## 15. Approval

| Role | Name | Status |
|---|---|---|
| Tester | Salma Mizar | Prepared |
