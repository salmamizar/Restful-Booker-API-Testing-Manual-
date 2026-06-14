# Restful Booker API Manual Testing

This repository contains manual API testing documentation and Postman artifacts for the Restful Booker API.

## Project Overview

Restful Booker is a public REST API used for practicing API testing. This project validates the main API functionalities such as authentication, booking creation, retrieving bookings, filtering, updating, partial updating, deleting bookings, and full end-to-end booking lifecycle.

## Application Under Test

**Base URL:** `https://restful-booker.herokuapp.com`  
**API Type:** REST API  
**Data Format:** JSON  
**Authentication:** Token-based authentication using cookie token

## Repository Structure

```text
Restful-Booker-API-Manual-Testing
│
├── README.md
│
├── documentation
│   ├── Test_Plan.md
│   ├── Test_Cases.md
│   └── E2E_Scenarios.md
│
├── postman_artifacts
│   ├── RestfulBooker.postman_collection.json
│   └── RestfulBooker_ENV.postman_environment.json
│
└── test_execution
    └── Test_Execution_Report.xlsx
```

## Testing Scope

The manual testing scope includes:

- Authentication
- Create Booking
- Get Booking
- Filter Booking
- Full Update Booking using PUT
- Partial Update Booking using PATCH
- Delete Booking
- End-to-End Booking Lifecycle

## Testing Types Covered

- Functional API Testing
- Positive Testing
- Negative Testing
- Boundary Value Testing
- Data Type Validation
- Header Validation
- Authentication and Authorization Testing
- Schema / Contract Testing
- End-to-End API Testing
- Basic Response Time Check

## Tools Used

- Postman
- Microsoft Excel / Google Sheets
- GitHub
- Markdown Documentation

## Postman Environment Variables

| Variable | Description |
|---|---|
| `baseUrl` | Restful Booker base URL |
| `token` | Authentication token generated from `/auth` |
| `bookingId` | Booking ID generated from `/booking` |
| `firstname` | First name used for filter testing |
| `lastname` | Last name used for filter testing |
| `checkin` | Check-in date used for date filter testing |
| `checkout` | Check-out date used for date filter testing |

## Main API Endpoints Tested

| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth` | Generate authentication token |
| POST | `/booking` | Create new booking |
| GET | `/booking` | Get all booking IDs |
| GET | `/booking/{id}` | Get booking by ID |
| GET | `/booking?firstname=&lastname=` | Filter bookings |
| PUT | `/booking/{id}` | Full update booking |
| PATCH | `/booking/{id}` | Partial update booking |
| DELETE | `/booking/{id}` | Delete booking |

## End-to-End Flow

The E2E scenario validates the complete booking lifecycle:

1. Generate token
2. Create booking
3. Get created booking
4. Full update booking
5. Verify full update
6. Partial update booking
7. Verify partial update
8. Delete booking
9. Verify deleted booking returns 404

## Known API Behaviors

During testing, some API behaviors may differ from standard REST expectations:

- Invalid login may return `200` with `reason: Bad credentials`.
- Delete booking may return `201` instead of the common REST status `204`.
- Missing required fields may return `500` instead of `400`.
- Some validation rules may not be enforced by the API.

These behaviors should be documented in the execution report or defect report.

## How to Use This Repository

1. Review the test plan in `documentation/Test_Plan.md`.
2. Review the manual test cases in `documentation/Test_Cases.md`.
3. Import the Postman collection from `postman_artifacts`.
4. Import the Postman environment from `postman_artifacts`.
5. Execute the requests in Postman.
6. Record actual results in `test_execution/Test_Execution_Report.xlsx`.
7. Document defects or observations if actual behavior differs from expected behavior.

## Author

Mervat Ahmed
