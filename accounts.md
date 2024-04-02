# User Authentication API Documentation

## Introduction

The User Authentication API provides endpoints for user authentication, registration, updating user authentication information, and password management.

## Endpoints

### 1. User Authentication

#### URL

`POST http://localhost:8080/api/v1/auth/login`

#### Method

POST

#### Description

This endpoint is used for user authentication.

#### Request Body

- `email` (String, Required): The email address of the user.
- `password` (String, Required): The password of the user.

#### Response

- **Status:** 200
- **Content-Type:** application/json

### 2. Register New User

#### URL

`POST http://localhost:8080/api/v1/auth/register?institution_id=:institution_id`

#### Method

POST

#### Description

This endpoint is used to register a new user with the specified institution ID.

#### Query Parameters

- `institution_id` (Query Parameter): The unique identifier of the institution.

#### Request Body

- **firstName** (Text, Required): The first name of the user.
- **lastName** (Text, Required): The last name of the user.
- **email** (Text, Required): The email address of the user.
- **phone** (Text, Required): The phone number of the user.
- **image_url** (Text, Required): The URL of the user's image.

#### Response

- **Status Code:** `201 Created`
- **Content Type:** `application/json`

### 3. Update User Authentication Information

#### URL

`PATCH http://localhost:8080/api/v1/auth/:id`

#### Method

PATCH

#### Description

This endpoint is used to update the user's authentication information.

#### Request Body

- **firstName** (String, Optional): The updated first name of the user.
- **lastName** (String, Optional): The updated last name of the user.
- **phone** (String, Optional): The updated phone number of the user.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

### 4. Retrieve List of Administrators

#### URL

`GET http://localhost:8080/api/v1/auth/admins/`

#### Method

GET

#### Description

This endpoint is used to retrieve a list of administrators.

#### Request Parameters

- **take** (Query Parameter): The number of records to retrieve.
- **skip** (Query Parameter): The number of records to skip.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

### 5. Forgot Password Update

#### URL

`PATCH http://localhost:8080/api/v1/auth/user/forgot-password`

#### Method

PATCH

#### Description

This endpoint is used to update the password for a user who has forgotten their password.

#### Request Body

- **email** (String, Required): The email address of the user.
- **otp** (String, Required): The one-time password received by the user.
- **newPassword** (String, Required): The new password to set for the user.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

### 6. Verify OTP for Forgot Password

#### URL

`POST http://localhost:8080/api/v1/auth/user/verify-forgot-password-otp`

#### Method

POST

#### Description

This endpoint is used to verify the OTP (One Time Password) sent to the user's email for the forgot password process.

#### Request Body

- **email** (String, Required): The email address of the user.
- **otp** (String, Required): The one-time password received by the user.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

### 7. Patch User Forgot Password New Password

#### URL

`PATCH http://localhost:8080/api/v1/auth/user/patch-forgot-password`

#### Method

PATCH

#### Description

This endpoint is used to update the password for a user who has forgotten their password. It requires the user's email, OTP (One Time Password), and the new password.

#### Request Body

- **email** (String, Required): The email address of the user.
- **otp** (String, Required): The one-time password received by the user.
- **newPassword** (String, Required): The new password to set for the user.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json
