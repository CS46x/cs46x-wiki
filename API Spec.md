_Owner: Team | Last updated: 2026-02-19 | Status: Draft_

# API Spec

## Purpose
Define authentication and account management endpoints including password change and reset flows.

## Base URL(s)
- Dev: /api
- Staging: TBD
- Prod: TBD

## Authentication
- JWT Bearer Token required for authenticated endpoints (e.g., Change Password).
- Password reset endpoints do not require authentication but require valid reset token.


## Endpoints
### `GET /tbd`
- Purpose: Allow authenticated users to change their password.
- Response: 200 OK – Password successfully changed

### `POST /tbd`
- Purpose: TBD
- Request: TBD
- Response: TBD

### POST /account/change-password

- Purpose: Allow authenticated users to change their password.
- Authentication: Required (JWT)
- Request Body:
{
  "currentPassword": "string",
  "newPassword": "string",
  "confirmNewPassword": "string"
}
- Response:
	•	200 OK – Password successfully changed
	•	400 Bad Request – Validation failure
	•	401 Unauthorized – Invalid or missing token

### POST /account/reset-password
- Purpose: Request a password reset email/token.
- Authentication: Not required
- Request Body:
{
  "email": "string"
}
- Response:
	•	200 OK – Reset request processed
	•	400 Bad Request – Invalid email

### POST /account/confirm-reset
- Purpose: Confirm password reset using token and set new password.
- Authentication: Not required (token-based)
- Request Body:
{
  "email": "string",
  "token": "string",
  "newPassword": "string",
  "confirmNewPassword": "string"
}
- Response:
	•	200 OK – Password successfully reset
	•	400 Bad Request – Invalid token or validation failure

