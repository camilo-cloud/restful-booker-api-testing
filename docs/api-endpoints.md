# API Endpoints - Restful Booker

**Base URL:** `https://restful-booker.herokuapp.com`

| Endpoint | Purpose | Method | Path | Auth Required | Request Content-Type | Response Content-Type | Request Body | Success Status | Success Response | Common Error Responses | Notes |
|----------|---------|--------|------|---------------|----------------------|-----------------------|--------------|----------------|------------------|------------------------|-------|
| Health Check | Verify API availability | GET | `/ping` | No | N/A | `text/plain` | None | `201 Created` | `Created` | N/A | Used to verify that the API is running. |
| Create Token | Generate an authentication token | POST | `/auth` | No | `application/json` | `application/json` | `username`, `password` | `200 OK` | `token` | Invalid credentials (response body) | |
| Create Booking | Create a new booking | POST | `/booking` | No | `application/json` | `application/json` | `firstname`, `lastname`, `totalprice`, `depositpaid`, `bookingdates`, `additionalneeds` | `200 OK` | `bookingid` + booking object | `400 Bad Request` | |
| Get Booking IDs | Retrieve booking IDs | GET | `/booking` | No | N/A | `application/json` | None | `200 OK` | Array of booking IDs | N/A | Supports query parameters such as `firstname`, `lastname`, `checkin`, and `checkout`. |
| Get Booking | Retrieve a booking | GET | `/booking/{id}` | No | N/A | `application/json` | None | `200 OK` | Booking object | `404 Not Found` | |
| Update Booking | Replace an existing booking | PUT | `/booking/{id}` | Yes | `application/json` | `application/json` | Full booking object | `200 OK` | Updated booking object | `403 Forbidden` | Requires token (Cookie) or Basic Auth. |
| Partial Update Booking | Update specific booking fields | PATCH | `/booking/{id}` | Yes | `application/json` | `application/json` | One or more booking fields | `200 OK` | Updated booking object | `403 Forbidden` | Requires token (Cookie) or Basic Auth. |
| Delete Booking | Delete a booking | DELETE | `/booking/{id}` | Yes | N/A | `text/plain` | None | `201 Created` | `Created` | `403 Forbidden` | Requires token (Cookie) or Basic Auth. |
