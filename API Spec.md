_Owner: Team | Last updated: 2026-03-09 | Status: Draft_

# API Spec

## Purpose
Define authentication and account management endpoints including password change and reset flows.

## Base URL(s)
- Dev: https://localhost:5000
- Prod: https://client.arenaraid.com

## Authentication Endpoints
- JWT Bearer Token required for authenticated endpoints (e.g., Change Password).
- Password reset endpoints do not require authentication but require valid reset token.

`POST /api/oauth/token`

#### Login Payload
```
{
    "username":"your_username",
    "password":"your_password"
}
```

#### Successful Login
```
{
    "expires_In": "2026-02-10T18:26:42.576406Z",
    "token_Type": "bearer",
    "access_Token": "valid_access_token"
}
```

## Account Endpoints

### `POST /api/account/register`
- Purpose: Register a new user account.
- Authentication: Not required
- Request Body:
```json
{
  "userName": "string",
  "password": "string",
  "confirmPassword": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "phoneNumber": "string"
}
```
- Responses:
  - `200 OK` – Account created
  - `400 Bad Request` – Validation failure or username/email already taken

---

### `POST /api/account/password/reset`
- Purpose: Request a password reset email/token.
- Authentication: Not required
- Request Body:
```json
{
  "email": "string",
  "requestedMethod": 0
}
```
- Responses:
  - `200 OK` – Reset request processed (email/SMS sent)
  - `401 Unauthorized` – User not found

---

### `POST /api/account/password/confirm`
- Purpose: Confirm password reset using token and set new password.
- Authentication: Not required (token-based)
- Request Body:
```json
{
  "userName": "string",
  "resetToken": "string",
  "password": "string",
  "confirmPassword": "string",
  "resetMethod": 0
}
```
- Error Responses:
  - `200 OK` – Password successfully reset
  - `400 Bad Request` – Identity validation failure
  - `401 Unauthorized` – User not found
  - `422 Unprocessable Entity` – Invalid or expired reset token

---

### `POST /api/account/password/change`
- Purpose: Allow authenticated users to change their password.
- Authentication: Required (JWT)
- Request Body:
```json
{
  "currentPassword": "string",
  "newPassword": "string",
  "confirmNewPassword": "string"
}
```
- Response:
	•	200 OK – Password successfully changed
	•	400 Bad Request – Validation failure
	•	401 Unauthorized – Invalid or missing token

---

### `POST /api/account/email/change`
- Purpose: Change the authenticated user's email address. If the username previously matched the old email it is updated to match.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "newEmail": "string",
  "password": "string"
}
```
- Success Response `200 OK`:
```json
{ "message": "Email updated." }
```
- Error Responses:
  - `400 Bad Request` – Validation failure
  - `401 Unauthorized` – Invalid or missing token

---

### `GET /api/account/profile`
- Purpose: Get the authenticated user's profile.
- Authentication: **Required (JWT)**
- Success Response `200 OK`:
```json
{
  "id": "string",
  "userName": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "bio": "string",
  "pronouns": "string",
  "avatarId": 1,
  "created": "2026-01-01T00:00:00Z"
}
```
- Error Responses:
  - `401 Unauthorized` – Invalid or missing token

---

### `PUT /api/account/profile`
- Purpose: Update the authenticated user's profile.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "bio": "string",      // max 200 chars, optional
  "pronouns": "string", // max 50 chars, optional
  "avatarId": 1         // integer 1–16
}
```
- Success Response `200 OK`: Same as `GET /api/account/profile`
- Error Responses:
  - `401 Unauthorized` – Invalid or missing token

---

## Arena Endpoints

> Arenas are persistent lobby/room configurations stored in the database. Temporary (non-static) rooms exist only in Redis while the session is active.

### `GET /api/arenas`
- Purpose: Get all top-level lobby arenas.
- Authentication: Not required
- Success Response `200 OK`: Array of `ArenaConfiguration` objects.

`ArenaConfiguartion`:
```json
{
  "guid": "string",
  "parentGuid": "string",
  "parent": "object",
  "name": "string",
  "description": "string",
  "motd": "string",
  "password": "string",
  "imageUrl": "string",
  "ownerId": "string",
  "isOfficial": "boolean",
  "isPublic": "boolean",
  "isStatic": "boolean",
  "hasVoice": "boolean",
  "hasVideo": "boolean",
  "hasImages": "boolean",
  "createdAt": "string",
  "arenas": "array",
  "members": "array"
}
```

---

### `GET /api/arenas/{guid}`
- Purpose: Get a specific arena by its GUID.
- Authentication: Not required
- Path Parameters: `guid` – arena GUID
- Success Response `200 OK`: `ArenaConfiguration` object.

---

### `POST /api/arenas`
- Purpose: Create a new arena configuration.
- Authentication: Not required
- Request Body:
```json
{
  "name": "string",
  "description": "string",
  "motd": "string",
  "password": "string",
  "imageUrl": "string",
  "ownerId": "string",
  "isOfficial": false,
  "isPublic": true,
  "isStatic": false,
  "hasVoice": false,
  "hasVideo": false,
  "hasImages": false
}
```
- Success Response `201 Created`: The created `ArenaConfiguration` with `Location` header pointing to `GET /api/arenas/{guid}`.
- Error Responses:
  - `400 Bad Request` – Validation failure

---

### `PUT /api/arenas/{guid}`
- Purpose: Update an existing arena configuration. *(Partially implemented)*
- Authentication: Not required
- Path Parameters: `guid` – Arena GUID
- Request Body: Same shape as `POST /api/arenas` but with updated info
- Success Response `200 OK`: The updated `ArenaConfiguration`.

---

### `DELETE /api/arenas/{guid}`
- Purpose: Delete an arena configuration *(Partially implemented)*
- Authentication: Not required
- Path Parameters: `guid` – Arena GUID
- Success Response `204 No Content`

---

## Friends Endpoints

### `GET /api/friends`
- Purpose: Get the full friends list for the user.
- Authentication: **Required (JWT)**
- Success Response `200 OK`: Array of friend objects:
```json
[
  {
    "friendId": "string",
    "userName": "string",
    "firstName": "string",
    "lastName": "string",
    "groupName": "string",
    "since": "2026-01-01T00:00:00Z",
    "avatarId": 1,
    "status": "Online",
    "bio": "string",
    "pronouns": "string"
  }
]
```
- Error Responses:
  - `401 Unauthorized`

---

### `GET /api/friends/requests`
- Purpose: Get all pending friend requests for the user.
- Authentication: **Required (JWT)**
- Success Response `200 OK`: Array of friend request objects:
```json
[
  {
    "otherUserId": "string",
    "otherUserName": "string",
    "comment": "string",
    "created": "2026-01-01T00:00:00Z",
    "direction": "incoming",  // either "incoming" or "outgoing"
    "avatarId": 1
  }
]
```
- Error Responses:
  - `401 Unauthorized`

---

### `POST /api/friends/request/send`
- Purpose: Send a friend request to another user.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "toUserId": "string",
  "comment": "string" // optional
}
```
- Success Response `200 OK`:
```json
{
  "fromUserId": "string",
  "toUserId": "string",
  "comment": "string",
  "created": "2026-01-01T00:00:00Z"
}
```
- Error Responses:
  - `401 Unauthorized`
  - `404 Not Found` – Target user does not exist
  - `409 Conflict` – Already friends, or there is already a pending request

---

### `POST /api/friends/request/accept`
- Purpose: Accept a pending incoming friend request.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "otherUserId": "string"
}
```
- Success Response `200 OK`:
```json
{
  "userId": "string",
  "friendId": "string"
}
```
- Error Responses:
  - `401 Unauthorized`
  - `404 Not Found` – Friend request not found

---

### `POST /api/friends/request/decline`
- Purpose: Decline a pending incoming friend request.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "otherUserId": "string"
}
```
- Success Response `200 OK`:
```json
{
  "byUserId": "string",
  "otherUserId": "string"
}
```
- Error Responses:
  - `401 Unauthorized`
  - `404 Not Found` – Friend request not found

---

### `DELETE /api/friends/remove`
- Purpose: Remove an existing friendship.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "otherUserId": "string"
}
```
- Success Response `200 OK`:
```json
{
  "byUserId": "string",
  "friendId": "string"
}
```
- Error Responses:
  - `401 Unauthorized`
  - `404 Not Found` – Friendship not found

---

### `POST /api/friends/search`
- Purpose: Search for users by username, first name, or last name. The calling user is excluded from results.
- Authentication: **Required (JWT)**
- Request Body:
```json
{
  "searchTerm": "string" // minimum 2 characters
}
```
- Success Response `200 OK`: Array of matching user objects.
- Error Responses:
  - `400 Bad Request` – Search term too short (< 2 chars)
  - `401 Unauthorized`

---

## Health Check

### `GET /api/healthcheck`
- Purpose: Confirm the service is running.
- Authentication: Not required
- Success Response `200 OK`

---

## SignalR Hubs

SignalR connections require a valid jwt token passed as a query parameter or in the `Authorization` header during the handshake.

```
wss://<host>/chat?access_token=<jwt>
wss://<host>/messengerhub?access_token=<jwt>
```

---

### Hub: `/chat` — ChatHub

Used for arena group chat, room management, and lobby presence.

#### Client --> Server Methods

| Method | Parameters | Description |
|--------|-----------|-------------|
| `Join` | `id: string, password: string` | Join an arena (lobby or room) by GUID. Pass an empty string for unprotected arenas. |
| `Create` | `model: Arena` | Create a new sub-arena inside the current arena. |
| `Update` | `model: ArenaConfiguration` | Update an arena's settings. Admin/owner only. |
| `Send` | `message: Message` | Send a chat message to the current arena. |
| `SendAction` | `text: string` | Send anaction message to the current arena. |
| `SetStatus` | `status: OnlineStatus` | Update the caller's online status. |
| `Kick` | `id: string` | Kick a user by their user ID. Admin/owner only. |
| `SystemMessage` | `text: string` | Broadcast a system message to all connected users. Admin only. |

#### Server --> Client Events

| Event | Payload | Description |
|-------|---------|-------------|
| `message` | `Message` | A new chat message was sent to the arena. |
| `sendAction` | `string` | A `/me`-style action message. |
| `addArena` | `ArenaCard` | A new sub-arena was created inside the current lobby. |
| `updateArena` | `Arena` | A sub-arena's configuration was updated. |
| `update` | `Arena` | The current arena's configuration was updated. This info is sent to all arena members. |
| `updateUser` | `ArenaUser` | A user in the arena updated their status or info. |
| `kicked` | `string` (arena GUID or `""`) | The client has been kicked. If a GUID is provided, redirect to that arena. |
| `systemmessage` | `string` | A system-level message. |

---

### Hub: `/messengerhub` — MessengerHub

Used for direct messaging and friend notifications.

#### Client --> Server Methods

| Method | Parameters | Description |
|--------|-----------|-------------|
| `SendDirectMessage` | `toUserId: string, text: string` | Send a direct message to another user. Both users must be friends.|

#### Server --> Client Events

| Event | Payload | Description |
|-------|---------|-------------|
| `directMessage` | `{ from, fromName, to, text, sentAt }` | A direct message was received |
| `friendsList` | Array of `FriendResponseModel` | The caller's current friends list. This is triggered on connect and after any friendship change. |
| `friendRequestsList` | Array of `FriendRequestResponseModel` | The caller's pending friend requests. Triggered on connect and after any request change. |
| `friendStatusChanged` | `{ userId: string, status: string }` | A friend's online status changed. |
| `systemmessage` | `string` | A system-level message. |

