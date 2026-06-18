## Scope

### In Scope
- Health Check (`/ping`)
- Authentication (`/auth`) — positive and negative login scenarios
- Booking CRUD operations: Create, Read, Update, Partial Update, Delete
- Status code validation across all endpoints
- Data integrity validation (e.g., confirming the booking returned matches the requested ID)
- Negative testing across all endpoints (invalid IDs, missing required fields, invalid data types, requests without a valid auth token)
- JSON request/response format only

### Out of Scope
- XML request/response format (supported by the API, but excluded from this project's scope)
- UX / UI testing
- Performance / load testing
- Security testing (beyond basic authentication validation)

### Tools
- Postman — test design and manual execution
- Newman — automated execution and HTML reporting
