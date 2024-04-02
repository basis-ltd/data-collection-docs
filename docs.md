# Data Collection Documentation

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

# Categories API Documentation

## Introduction

The Categories API provides endpoints for managing categories in the system.

## Endpoints

# Endpoint: Create Category

## URL

`localhost:8080/api/v1/categories/`

## Method

POST

## Description

### Add Category

This endpoint allows you to create a new category.

#### Request Body

- name (string, required): The name of the category.

#### Response

- 201 Created: The category was successfully created.
    - success (boolean): Indicates if the request was successful.
    - data (object): Information about the created category.
        - name (string): The name of the category.
        - deletedAt (string): Date and time when the category was deleted, if applicable.
        - id (string): The unique identifier of the category.
        - isActive (boolean): Indicates if the category is active.
        - createdAt (string): Date and time when the category was created.
        - updatedAt (string): Date and time when the category was last updated.

```json
{
  "name": "Media & Personality"
}
```

## Endpoint: Update Category

## URL

`localhost:8080/api/v1/categories/:id`

## Method

PATCH

## Description

# Endpoint: Update Category by ID

## URL

`http://localhost:8080/api/v1/categories/:id`

## Method

PATCH

## Description

This endpoint allows you to update a specific category by ID.

## Request

- **Method:** PUT
- **Endpoint:** `http://localhost:8080/api/v1/categories/:id`
- **Headers:**
    - **Content-Type:** application/json
- {"name": "*"}
    

## Response

- **Status Code:** 200 OK
- **Content Type:** application/json

### Response Body

```json
{
  "success": true,
  "data": {
    "id": "*****",
    "name": "*****",
    "isActive": true,
    "createdAt": "*****",
    "updatedAt": "*****",
    "deletedAt": null
  }
}
```

## Notes

- The request should be a PUT method.
- The endpoint URL should include the category ID (`:id`).
- The request headers should include "Content-Type: application/json".
- The request body should be in raw JSON format with the "name" key representing the updated category name.
- The response has a status code of 200, indicating a successful update.
- The Content-Type is set to application/json.
- The success flag indicates the success of the update.
- The response body includes a "data" object with information about the updated category, including id, name, isActive (indicates if the category is active), createdAt (date and time when the category was created), updatedAt (date and time when the category was last updated), and deletedAt (date and time when the category was deleted, if applicable).

---

# Endpoint: Retrieve List of Categories

## URL

`http://localhost:8080/api/v1/categories/`

## Method

GET

## Description

This endpoint makes an HTTP GET request to retrieve a list of categories. The request should include query parameters "take" to specify the number of items to retrieve, and "skip" to specify the number of items to skip.

## Request Parameters

- **take** (Number): The number of items to retrieve.
    
- **skip** (Number): The number of items to skip.
    

## Response

- **Status Code:** 200 OK
    
- **Content Type:** application/json
    

### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "name": "*****",
        "isActive": true,
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": null
      },
      // ... more category objects
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/categories/`.
    
- The request may include query parameters "take" and "skip" to control the number of items to retrieve and skip.
    
- The response has a status code of 200, indicating a successful request.
    
- The Content-Type is set to application/json.
    
- The "success" flag indicates the success of the request.
    
- The "data" object includes an array of category objects ("rows"), each containing "id", "name", "isActive" (indicates if the category is active), "createdAt" (date and time when the category was created), "updatedAt" (date and time when the category was last updated), and "deletedAt" (date and time when the category was deleted, if applicable) properties.
    
- Additionally, the "data" object includes "totalCount" (total count of categories), "totalPages" (total number of pages), and "currentPage" (current page number).

---

# Endpoint: Delete Category

## URL

`http://localhost:8080/api/v1/categories/:id`

## Method

DELETE

## Description

# Endpoint: Delete Category by ID

## URL

`http://localhost:8080/api/v1/categories/:id`

## Method

DELETE

## Description

This endpoint is used to delete a specific category by its ID.

## Request

- **Method:** DELETE
    
- **URL:** `http://localhost:8080/api/v1/categories/:id`
    

## Response

- **Status Code:** 204 No Content
    
- **Content Type:** text/xml
    
- **Body:** null
    

## Notes

- The request should be a DELETE method.
    
- The endpoint URL should include the category ID (`:id`).
    
- The response has a status code of 204, indicating a successful deletion.
    
- The Content-Type is set to text/xml.
    
- The response body is null, as indicated by the "Body: null".

# Institutions API Documentation

## Introduction

The Institutions API provides endpoints for managing institutions in the system.

## Endpoints

# Endpoint: Add Institution

## URL

`http://localhost:8080/api/v1/institutions/`

## Method

POST

## Description

This endpoint allows the addition of a new institution.

## Request

- **Method:** POST
    
- **URL:** `http://localhost:8080/api/v1/institutions/`
    

### Request Body

- **name** (string, required): The name of the institution.
    
- **address** (string, required): The address of the institution.
    
- **phone** (string, required): The phone number of the institution.
    
- **category_id** (string, required): The category ID of the institution.
    
- **email** (string, required): The email address of the institution.
    
- **logo** (string, optional): The logo of the institution.
    

## Response

- **Status Code:** 201 Created
    
- **Content Type:** application/json
    

### Response Body

```json
{
  "success": true,
  "data": {
    "name": "*****",
    "address": "*****",
    "email": "*****",
    "phone": "*****",
    "category_id": "*****",
    "logo": null,
    "category_name": "*****",
    "deletedAt": null,
    "id": "*****",
    "isActive": true,
    "createdAt": "*****",
    "updatedAt": "*****"
  }
}
```

## Notes

- The request should be a POST method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/institutions/`.
    
- The request body should include parameters for the institution's name, address, phone, category ID, email, and an optional logo.
    
- The response has a status code of 201, indicating the successful creation of the institution.
    
- The Content-Type is set to application/json.
    
- The response body includes a "success" flag and a "data" object containing details related to the added institution, including its name, address, email, phone, category ID, logo, category name, and other metadata.

---

# Endpoint: Retrieve List of Institutions

## URL

`http://localhost:8080/api/v1/institutions/`

## Method

GET

## Description

This API endpoint makes an HTTP GET request to retrieve a list of institutions. The request should be sent to `http://localhost:8080/api/v1/institutions/` with query parameters for pagination, where "take" specifies the number of items to retrieve and "skip" specifies the number of items to skip.

## Request Parameters

### Query Parameters

- **take** (number): The number of items to retrieve.
    
- **skip** (number): The number of items to skip.
    

## Response

- **Status Code:** 200 OK
    
- **Content Type:** application/json
    

### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "name": "*****",
        "email": "*****",
        "logo": "*****",
        "address": "*****",
        "category_id": "*****",
        "category_name": "*****",
        "isActive": true,
        "phone": "*****",
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": "*****"
      },
      // ... more institution details
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/institutions/`.
    
- Query parameters for pagination can be adjusted as needed (`?take=5&skip=0`).
    
- The response has a status code of 200, indicating a successful request.
    
- The Content-Type is set to application/json.
    
- The response body includes a "success" flag and a "data" object with an array of institution records (named "rows"), each containing various details such as the institution's ID, name, email, logo, address, category ID, category name, activity status, phone, creation timestamp, update timestamp, and deletion timestamp. Additionally, the response includes metadata such as "totalCount", "totalPages", and "currentPage" for pagination.

# Endpoint: Update Institution Details

## URL

`http://localhost:8080/api/v1/institutions/:id`

## Method

PATCH

## Description

This endpoint is used to update the details of a specific institution.

## Request Parameters

- **name** (text): The updated name of the institution.
    
- **file** (file): The updated logo of the institution.
    
- **address** (text): The updated address of the institution.
    
- **email** (text): The updated email address of the institution.
    
- **category_id** (text): The updated category ID of the institution.
    

## Response

- **Status Code:** 200 OK
    
- **Content Type:** application/json
    

### Response Body

```json
{
  "success": true,
  "data": {
    "id": "*****",
    "name": "*****",
    "email": "*****",
    "logo": "*****",
    "address": "*****",
    "category_id": "*****",
    "category_name": "*****",
    "isActive": true,
    "phone": "*****",
    "createdAt": "*****",
    "updatedAt": "*****",
    "deletedAt": "*****"
  }
}
```

## Notes

- The request should be a PATCH method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/institutions/:id`.
    
- The request parameters include the updated details of the institution, such as the name, logo, address, email, and category ID.
    
- The response has a status code of 200, indicating a successful update.
    
- The Content-Type is set to application/json.
    
- The response body includes a "success" flag and a "data" object with the updated details of the institution, including ID, name, email, logo, address, category ID, category name, status, phone, creation and update timestamps, and deletion status.

---

# Endpoint: Delete Institution by ID

## URL

`http://localhost:8080/api/v1/institutions/:id`

## Method

DELETE

## Description

This endpoint sends an HTTP DELETE request to delete the institution with the specified ID.

## Request

- **Method:** DELETE
    
- **URL:** `http://localhost:8080/api/v1/institutions/:id`
    

## Response

- **Status Code:** 204
    
- **Content Type:** text/xml
    

### Response Body

`null`

## Notes

- The request should be a DELETE method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/institutions/:id`.
    
- The response has a status code of 204, indicating a successful deletion.
    
- The Content-Type is set to text/xml.
    
- The response body is null.

---

# Endpoint: Get Institution Admins

## URL

`http://localhost:8080/api/v1/institutions/admins`

## Method

GET

## Description

This endpoint retrieves a list of institution admins with the ability to paginate the results.

## Request Parameters

- **take** (query parameter): The number of records to retrieve.
    
- **skip** (query parameter): The number of records to skip for pagination.
    

## Response

- **Status Code:** 200
    
- **Content Type:** application/json
    

### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "firstName": "*****",
        "lastName": "*****",
        "image_url": "*****",
        "email": "*****",
        "phone": "*****",
        "institution_id": "*****",
        "institution": {
          "id": "*****",
          "name": "*****",
          "logo": "*****"
        }
      },
      // Additional institution admin objects
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
    
- The endpoint URL should be `http://localhost:8080/api/v1/institutions/admins`.
    
- The request parameters include the number of records to retrieve (`take`) and the number of records to skip for pagination (`skip`).
    
- The response has a status code of 200, indicating a successful request.
    
- The Content-Type is set to application/json.
    
- The response body includes a "success" flag and a "data" object. The "data" object contains an array of institution admin objects (`rows`), each containing details such as ID, first name, last name, image URL, email, phone, institution ID, and more. Additionally, the response includes metadata such as `totalCount`, `totalPages`, and `currentPage` to facilitate pagination. Each institution admin object within the `rows` array also includes details about the associated institution.


# Projects API Documentation

## Introduction

The Projects API provides endpoints for managing projects in the system.

## Endpoints

# Endpoint: Add Project

## URL

`http://localhost:8080/api/v1/projects/`

## Method

POST

## Description

This endpoint allows you to create a new project.

## Request Body

- **title** (Text, Required): The title of the project.
  
- **description** (Text, Required): The description of the project.
  
- **start_date** (Text, Required): The start date of the project.
  
- **end_date** (Text, Optional): The end date of the project.

## Response

- **Status Code:** 201 Created
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "id": "*****",
    "title": "*****",
    "description": "*****",
    "status": "*****",
    "start_date": "*****",
    "end_date": "*****",
    "createdAt": "*****",
    "updatedAt": "*****",
    "institution": {
      "id": "*****",
      "name": "*****",
      "logo": "*****"
    },
    "admins": [
      {
        "id": "*****",
        "firstName": "*****",
        "lastName": "*****",
        "email": "*****",
        "image_url": "*****",
        "phone": "*****",
        "role": "*****",
        "isActive": true,
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": null
      },
      // ... more admin objects
    ]
  }
}
```

## Notes

- The request should be a POST method.
  
- The endpoint URL should be `http://localhost:8080/api/v1/projects/`.
  
- The request body should include details such as title, description, start date, and optional end date.
  
- The response has a status code of 201 Created, indicating the project was successfully created.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success of the request.
  
- The response body includes a "data" object with details of the newly created project, including ID, title, description, status, start and end dates, creation and update timestamps, and related institution and admins.

---

# Endpoint: Retrieve List of Projects with Pagination

## URL

`http://localhost:8080/api/v1/projects/?take=5&skip=0`

## Method

GET

## Description

This endpoint makes an HTTP GET request to retrieve a list of projects. The request includes query parameters for pagination, where "take" specifies the number of records to fetch, and "skip" specifies the number of records to skip.

## Request Parameters

- **take** (Number): The number of records to retrieve.
  
- **skip** (Number): The number of pages to skip.

## Response

- **Status Code:** 200 OK
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "title": "*****",
        "institution": {
          "id": "*****",
          "name": "*****",
          "logo": "*****"
        },
        "admins": [
          {
            "id": "*****",
            "firstName": "*****",
            "lastName": "*****",
            "image_url": "*****"
          },
          // ... more admin details
        ],
        "form": [
          // ... form details
        ],
        "start_date": "*****",
        "end_date": "*****",
        // ... more project attributes
      },
      // ... more project records
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
  
- The endpoint URL should include query parameters for pagination (`?take=5&skip=0`).
  
- The response has a status code of 200, indicating a successful request.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success of the request.
  
- The response body includes a "data" object with an array of project records (named "rows"), each containing various attributes such as id, title, institution details, form details, start and end dates, and other metadata. Additionally, the response includes "totalCount", "totalPages", and "currentPage" for pagination information. The "data" object also includes nested objects for "admins", "institution", and "form", providing detailed information about the administrators, institutions, and forms associated with the projects.

---

# Endpoint: Retrieve List of Projects with Pagination

## URL

`http://localhost:8080/api/v1/projects/?take=5&skip=0`

## Method

GET

## Description

This endpoint makes an HTTP GET request to retrieve a list of projects. The request includes query parameters for pagination, where "take" specifies the number of records to fetch, and "skip" specifies the number of records to skip.

## Request Parameters

- **take** (Number): The number of records to retrieve.
  
- **skip** (Number): The number of pages to skip.

## Response

- **Status Code:** 200 OK
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "title": "*****",
        "institution": {
          "id": "*****",
          "name": "*****",
          "logo": "*****"
        },
        "admins": [
          {
            "id": "*****",
            "firstName": "*****",
            "lastName": "*****",
            "image_url": "*****"
          },
          // ... more admin details
        ],
        "form": [
          // ... form details
        ],
        "start_date": "*****",
        "end_date": "*****",
        // ... more project attributes
      },
      // ... more project records
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
  
- The endpoint URL should include query parameters for pagination (`?take=5&skip=0`).
  
- The response has a status code of 200, indicating a successful request.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success of the request.
  
- The response body includes a "data" object with an array of project records (named "rows"), each containing various attributes such as id, title, institution details, form details, start and end dates, and other metadata. Additionally, the response includes "totalCount", "totalPages", and "currentPage" for pagination information. The "data" object also includes nested objects for "admins", "institution", and "form", providing detailed information about the administrators, institutions, and forms associated with the projects.

---

# Endpoint: Retrieve List of Projects with Pagination

## URL

`http://localhost:8080/api/v1/projects/?take=5&skip=0`

## Method

GET

## Description



This endpoint makes an HTTP GET request to retrieve a list of projects. The request includes query parameters for pagination, where "take" specifies the number of records to fetch, and "skip" specifies the number of records to skip.

## Request Parameters

- **take** (Number): The number of records to retrieve.
  
- **skip** (Number): The number of pages to skip.

## Response

- **Status Code:** 200 OK
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "title": "*****",
        "institution": {
          "id": "*****",
          "name": "*****",
          "logo": "*****"
        },
        "admins": [
          {
            "id": "*****",
            "firstName": "*****",
            "lastName": "*****",
            "image_url": "*****"
          },
          // ... more admin details
        ],
        "form": [
          // ... form details
        ],
        "start_date": "*****",
        "end_date": "*****",
        // ... more project attributes
      },
      // ... more project records
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
  
- The endpoint URL should include query parameters for pagination (`?take=5&skip=0`).
  
- The response has a status code of 200, indicating a successful request.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success of the request.
  
- The response body includes a "data" object with an array of project records (named "rows"), each containing various attributes such as id, title, institution details, form details, start and end dates, and other metadata. Additionally, the response includes "totalCount", "totalPages", and "currentPage" for pagination information. The "data" object also includes nested objects for "admins", "institution", and "form", providing detailed information about the administrators, institutions, and forms associated with the projects.

---

# Endpoint: Retrieve Project by ID

## URL

`http://localhost:8080/api/v1/projects/:id`

## Method

GET

## Description

This endpoint sends an HTTP GET request to `http://localhost:8080/api/v1/projects/:id` to retrieve details of a specific project identified by its ID.

## Response

- **Status Code:** 200 OK
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "id": "*****",
    "title": "*****",
    "description": "*****",
    "isActive": true,
    "form_id": "*****",
    "institution_id": "*****",
    "admin_id": "*****",
    "start_date": "*****",
    "end_date": "*****",
    "createdAt": "*****",
    "updatedAt": "*****",
    "deletedAt": null,
    "form": [
      // ... form details
    ],
    "institution": {
      "id": "*****",
      "name": "*****",
      "logo": "*****"
    },
    "admins": [
      {
        "id": "*****",
        "firstName": "*****",
        "lastName": "*****",
        "image_url": "*****"
      },
      // ... more admin details
    ]
  }
}
```

## Notes

- The request should be a GET method.
  
- The endpoint URL should include the project ID (`:id`).
  
- The response has a status code of 200, indicating a successful request.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success status of the request.
  
- The response body includes a "data" object with various details of the project, including ID, title, description, isActive status, form ID, institution ID, admin ID, start date, end date, creation timestamp, update timestamp, deletedAt timestamp, form array, institution object, and admins array.

---

# Endpoint: Update Project

This endpoint allows updating a specific project identified by the provided ID. The HTTP PATCH request should be sent to localhost:8080/api/v1/projects/:id with a JSON payload in the raw request body type. The payload should include the fields "title" and "description" to be updated.

### Request Body

- title (string, required): The updated title of the project.
- description (string, required): The updated description of the project.

### Response

- Status: 200
- Content-Type: application/json

```json
{
    "success": true,
    "data": {
        "id": "",
        "title": "",
        "description": "",
        "isActive": true,
        "form_id": null,
        "institution_id": "",
        "admin_id": "",
        "start_date": "",
        "end_date": null,
        "createdAt": "",
        "updatedAt": "",
        "deletedAt": null,
        "form": [],
        "institution": {
            "id": "",
            "name": "",
            "logo": ""
        },
        "admins": {
            "id": "",
            "firstName": "",
            "lastName": "",
            "image_url": null
        }
    }
}
```

The response contains a "success" flag indicating the success of the operation, and the "data" object with the updated project details.

---

# Endpoint: Delete Project by ID

## URL

`http://localhost:8080/api/v1/projects/:id`

## Method

DELETE

## Description

This endpoint sends an HTTP DELETE request to `http://localhost:8080/api/v1/projects/:id` to delete a project with the specified ID.

## Request

- **Method:** DELETE
  
- **URL:** `http://localhost:8080/api/v1/projects/:id`
  

## Response

- **Status Code:** 204 No Content
  
- **Content Type:** text/xml
  
- **Body:** null

## Notes

- The request should be a DELETE method.
  
- The endpoint URL should include the project ID (`:id`).
  
- The response has a status code of 204, indicating a successful deletion.
  
- The Content-Type is set to text/xml.
  
- The response body is null.

---

# Endpoint: Retrieve List of Users Associated with a Project

## URL

`http://localhost:8080/api/v1/projects/:projectId/users/?take=5&skip=0`

## Method

GET

## Description

This endpoint retrieves a list of users associated with a specific

 project, identified by the project ID. The query parameters allow for pagination, with the "take" parameter specifying the number of records to retrieve and the "skip" parameter specifying the number of records to skip.

## Request Parameters

- **projectId** (string): The unique identifier of the project.
  

### Query Parameters

- **take** (number): The number of records to retrieve.
  
- **skip** (number): The number of records to skip.

## Response

- **Status Code:** 200 OK
  
- **Content Type:** application/json
  
### Response Body

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "firstName": "*****",
        "lastName": "*****",
        "image_url": "*****",
        "email": "*****",
        "phone": "*****",
        "role": "*****"
      },
      // ... more user details
    ],
    "totalCount": "*****",
    "totalPages": "*****",
    "currentPage": "*****"
  }
}
```

## Notes

- The request should be a GET method.
  
- The endpoint URL should include the project ID (`:projectId`).
  
- Query parameters for pagination (`?take=5&skip=0`) can be adjusted as needed.
  
- The response has a status code of 200, indicating a successful request.
  
- The Content-Type is set to application/json.
  
- The success flag indicates the success of the request.
  
- The response body includes a "data" object with an array of user records (named "rows"), each containing various properties such as user ID, first name, last name, image URL, email, phone, and role. Additionally, the response includes metadata such as "totalCount", "totalPages", and "currentPage" for pagination.

# Forms API Documentation

## Introduction

The Forms API provides endpoints to manage forms within a project. You can create, update, delete, retrieve, and list forms, as well as retrieve form entries within a specified date range.

## Authentication

All endpoints require authentication using a bearer token. Include the access token in the authorization header as follows:

```
Authorization: Bearer {{access_token}}
```

## Endpoints

### 1. Create Form

#### URL

`POST http://localhost:8080/api/v1/forms?project_id=460caeb7-2527-4213-8dde-d0a08ccf53ef`

#### Method

POST

#### Description

This endpoint allows you to add a new form.

#### Request Body

```json
{
    "name": "Mobile Form",
    "visibility": "public",
    "target_entries": 3000,
    "description": "The mobile form for testing",
    "record_location": true
}
```

#### Response

- **Status Code:** 201 Created
- **Content Type:** application/json

```json
{
  "success": true,
  "data": {
    "name": "*****",
    "admin_id": "*****",
    "project_id": "*****",
    "visibility": "*****",
    "target_entries": "*****",
    "description": "*****",
    "recordLocation": true,
    "deletedAt": null,
    "id": "*****",
    "isActive": true,
    "createdAt": "*****",
    "updatedAt": "*****"
  }
}
```

#### Notes

- The request should be a POST method.
- The endpoint URL should include the project ID as a query parameter.
- The request body should include parameters such as `name`, `visibility`, `target_entries`, `description`, and `record_location`.
- The response has a status code of 201, indicating successful creation.
- The Content-Type is set to application/json.
- The response body includes a "success" flag and a "data" object with details of the newly created form.

### 2. Update Form

#### URL

`PATCH http://localhost:8080/api/v1/forms/:id`

#### Method

PATCH

#### Description

This endpoint allows you to update details of an existing form.

#### Request Body

```json
{
    "name": "Updated New Form",
    "record_location": true,
    "description": "This is an updated description my guyy",
    "target_entries": 1000,
    "visibility": "private"
}
```

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

```json
{
  "success": true,
  "data": {
    "progress": null,
    "totalEntries": 0,
    "id": "*****",
    "name": "*****",
    "description": "*****",
    "isActive": true,
    "target_entries": 0,
    "visibility": "*****",
    "project_id": "*****",
    "admin_id": "*****",
    "sections": [
      {
        "id": "*****",
        "name": "*****",
        "description": null,
        "order": 0,
        "is_required": true,
        "isActive": true,
        "form_id": "*****",
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": null,
        "fields": []
      }
    ],
    "updatedAt": "*****",
    "createdAt": "*****",
    "deletedAt": null,
    "recordLocation": true
  }
}
```

#### Notes

- The request should be a PATCH method.
- The endpoint URL should include the form ID.
- The request body should include parameters such as `name`, `record_location`, `description`, `target_entries`, and `visibility`.
- The response has a status code of 200, indicating successful update.
- The Content-Type is set to application/json.
- The response body includes a "success" flag and a "data" object with details of the updated form.

### 3. Get Form

#### URL

`GET http://localhost:8080/api/v1/forms/:id`

#### Method

GET

#### Description

This endpoint allows you to retrieve details of a form by its ID.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

```json
{
  "success": true,
  "data": {
    "progress": 0,
    "totalEntries": 0,
    "id": "*****",
    "name": "*****",
    "description": "*****",
    "isActive": true,
    "target_entries": 0,
    "visibility": "*****",
    "project_id": "*****",
    "admin_id": "*****",
    "sections": [
      {
        "id": "*****",
        "name": "*****",
        "description": null,
        "order": 0,
        "is_required": true,
        "isActive": true,
        "form_id": "*****",
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": null,
        "fields": []
      }
    ],
    "updatedAt": "*****",
    "createdAt": "*****",
    "deletedAt": null,
    "recordLocation": true
  }
}
```

#### Notes

- The request should be a GET method.
- The endpoint URL should include the form ID.
- The response has a status code of 200, indicating successful retrieval.
- The Content-Type is set to application/json.
- The response body includes a "success" flag and a "data" object with details of the form.

### 4. List Forms

#### URL

`GET http://localhost:8080/api/v1/forms?project_id=ddef0a52-e626-4311-a435-cad871f9e333&take=2&skip=0`

#### Method

GET

#### Description

This endpoint allows you to retrieve a list of forms associated with a project, with pagination.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

```json
{
  "success": true,
  "data": {
    "rows": [
      {
        "id": "*****",
        "name": "*****",
        "description": "*****",
        "target_entries": 0,
        "isActive": true,
        "recordLocation": true,
        "visibility": "*****",
        "project_id": "*****",
        "admin_id": "*****",
        "createdAt": "*****",
        "updatedAt": "*****",
        "deletedAt": null,
        "sections": [
          {
            "id": "*****",
            "name": "*****",
            "description": "*****",
            "order": 0,
            "is_required": true,
            "isActive": true,
            "form_id": "*****",
            "createdAt": "*****",
           

 "updatedAt": "*****",
            "deletedAt": null
          }
        ]
      }
    ],
    "count": 1
  }
}
```

#### Notes

- The request should be a GET method.
- The endpoint URL should include the project ID as a query parameter, along with pagination parameters `take` and `skip`.
- The response has a status code of 200, indicating successful retrieval.
- The Content-Type is set to application/json.
- The response body includes a "success" flag and a "data" object with a list of forms and a count of total forms.

### 5. Delete Form

#### URL

`DELETE http://localhost:8080/api/v1/forms/:id`

#### Method

DELETE

#### Description

This endpoint allows you to delete a form by its ID.

#### Response

- **Status Code:** 200 OK
- **Content Type:** application/json

```json
{
  "success": true,
  "message": "Form deleted successfully"
}
```

#### Notes

- The request should be a DELETE method.
- The endpoint URL should include the form ID.
- The response has a status code of 200, indicating successful deletion.
- The Content-Type is set to application/json.
- The response body includes a "success" flag and a message confirming successful deletion.

# Fields API Documentation

## Introduction

This documentation provides details for interacting with the API endpoints related to managing form fields.


### 1. Create Form Fields

- **Description:** Add fields to a form.

- **URL:** `http://localhost:8080/api/v1/fields`

- **Method:** POST

- **Request:**

  ```json
  {
    "fields": [
      {
        "label": "Full Name",
        "placeholder": "John Doe",
        "is_required": true,
        "field_type": "text",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149"
      },
      {
        "label": "Gender",
        "placeholder": null,
        "is_required": true,
        "field_type": "radio",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "options": ["Male", "Female", "Other"],
        "default_value": "Other"
      },
      {
        "label": "Profile Picture",
        "placeholder": null,
        "is_required": true,
        "field_type": "file",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": null
      },
      {
        "label": "Contact Number",
        "placeholder": "Enter your phone number",
        "is_required": true,
        "field_type": "tel",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      },
      {
        "label": "Personal Website",
        "placeholder": "URL of your website",
        "is_required": false,
        "field_type": "url",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      },
      {
        "label": "Email Address",
        "placeholder": "Enter your email",
        "is_required": true,
        "field_type": "email",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      },
      {
        "label": "Birthday",
        "placeholder": "Select your birth date",
        "is_required": true,
        "field_type": "date",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      },
      {
        "label": "Age",
        "placeholder": "Enter your age",
        "is_required": true,
        "field_type": "number",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      },
      {
        "label": "Your Bio",
        "placeholder": "Tell us about yourself",
        "is_required": false,
        "field_type": "textarea",
        "section_id": "993cb400-ba18-4481-9b24-d5e83b0ff149",
        "default_value": ""
      }
    ],
    "form_id": "abee05b3-fddf-444c-a1ef-c9f15c572bd3"
  }
  ```

- **Response:**

  ```json
  {
    "success": true,
    "data": [
      {
        "label": "Field Label",
        "placeholder": "Field Placeholder",
        "field_type": "text",
        "default_value": "Default Value",
        "is_required": true,
        "isActive": true,
        "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82",
        "section_id": "",
        "deletedAt": null,
        "id": "GeneratedID",
        "createdAt": "2024-02-15T12:00:00Z",
        "updatedAt": "2024-02-15T12:00:00Z"
      }
    ]
  }
  ```

- **Notes:**
  - The request method should be POST.
  - The endpoint URL should be `http://localhost:8080/api/v1/fields`.
  - Query parameter `form_id` is required and should be the ID of the form to which the fields are to be added.
  - The request body should include a JSON payload with an array of field objects.
  - Each field object should have properties like `label`, `placeholder`, `is_required`, `field_type`, and `default_value`.
  - The response includes a success flag and an array of field objects with details of the added fields.

---

### 2. List Form Fields

- **Description:** Get fields by form ID.

- **URL:** `http://localhost:8080/api/v1/fields/?form_id=62bac6ad-9a67-4711-bced-c362afd3de82&take=10&skip=0`

- **Method:** GET

- **Request:**

  ```json
  No request body required.
  ```

- **Response:**

  ```json
  {
    "success": true,
    "data": {
      "rows": [
        {
          "id": "field1",
          "label": "Field 1",
          "placeholder": "Enter Field 1",
          "field_type": "text",
          "options": null,
          "is_required": true,
          "isActive": true,
          "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82",
          "section_id": "",
          "createdAt": "2024-02-15T12:00:00Z",
          "updatedAt": "2024-02-15T13:00:00Z",
          "deletedAt": null
        },
        {
          "id": "field2",
          "label": "Field 2",
          "placeholder": "Enter Field 2",
          "field_type": "number",
          "options": ["Option1", "Option2"],
          "is_required": false,
          "isActive": true,
          "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82",
          "section_id": "",
          "createdAt": "2024-02-15T12:30:00Z",
          "updatedAt": "2024-02-15T13:30:00Z",
          "deletedAt": null
        }
      ],
      "totalCount": 2,
      "totalPages": 1,
      "currentPage": 1
    }
  }
  ```

- **Notes:**
  - The request method should be GET.
  - The endpoint URL should be `http://localhost:8080/api/v1/fields?form_id=62bac6ad-9a67-4711-bced-c362afd3de82&take=10&skip=0`.
  - The response includes a success flag

 and an object with retrieved fields and pagination information.
  - Each field object in the "rows" array contains details such as `id`, `label`, `placeholder`, `field_type`, `options`, `is_required`, `isActive`, `form_id`, `section_id`, `createdAt`, `updatedAt`, and `deletedAt`.

---

### 3. Update Field

- **Description:** Update field by ID.

- **URL:** `http://localhost:8080/api/v1/fields/:id`

- **Method:** PATCH

- **Request:**

  ```json
  {
    "options": [1, 2, 4],
    "field_type": "select"
  }
  ```

- **Response:**

  ```json
  {
    "success": true,
    "data": {
      "id": "abc123",
      "label": "Updated Label",
      "placeholder": "Updated Placeholder",
      "field_type": "text",
      "options": ["Option1", "Option2"],
      "is_required": true,
      "default_value": "Updated Default Value",
      "isActive": true,
      "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82",
      "section_id": "",
      "createdAt": "2024-02-15T12:00:00Z",
      "updatedAt": "2024-02-15T13:00:00Z",
      "deletedAt": null
    }
  }
  ```

- **Notes:**
  - The request method should be PATCH.
  - The endpoint URL should be `http://localhost:8080/api/v1/fields/:id`.
  - The request body should include a JSON payload with properties like `label`, `placeholder`, `is_required`, `field_type`, `default_value`, and `options`.
  - The response includes a success flag and an object with details of the updated field.

---

### 4. Delete Form Fields

- **Description:** Delete fields by IDs.

- **URL:** `http://localhost:8080/api/v1/fields`

- **Method:** DELETE

- **Request:**

  ```json
  {
    "fields": [
      {"id": "field1"},
      {"id": "field2"}
    ]
  }
  ```

- **Response:**

  - **Status Code:** 204
  - **Content Type:** text/xml

- **Notes:**
  - The request method should be DELETE.
  - The endpoint URL should be `http://localhost:8080/api/v1/fields`.
  - The request body should include an array of field objects with their respective IDs.
  - The response includes a status code of 204 with a content type of text/xml, indicating a successful deletion.

# Form entries API Documentation

## Introduction

This documentation provides details for interacting with the API endpoints related to managing form entries.

## Endpoints

### 1. Create Entry 

* **Description:**  Add a new entry to a specified form.

* **URL:**  `http://localhost:8080/api/v1/form-entries/` 

* **Method:** POST

* **Authentication:** Bearer Token

*  **Request Body (JSON):**

   ```json
   {
       "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82" 
   }
   ```

* **Response:**

   * **Status Code:** 201 (Created)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "data": {
          "id": "entry_id",  // ID of created entry
          "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82", 
          "createdAt": "2024-04-03T10:00:00Z",
          "updatedAt": "2024-04-03T10:00:00Z" 
        }
      }
      ```

**Notes**

* The `form_id` is required within the request body.
* Ensure the provided `form_id` corresponds to an existing form.
* The response body will include the details of the newly created entry.

# Field Data API Documentation

## Introduction

This documentation provides details for interacting with the API endpoints for managing form field data.

## Endpoints

### 1. Create Field Data

* **Description:**  Add field data to a form.

* **URL:**  `/api/v1/field-data`  

* **Method:** POST

* **Authentication:** Bearer Token

*  **Request:**

   ```json
   {
       "form_id": "62bac6ad-9a67-4711-bced-c362afd3de82",
       "files": "c378830b-1328-4b83-89aa-bd48ea24f8e6", // File data
       "3c508a92-fb7d-4bb0-9694-5ba05b2d24cc": "This is a description field",
       "3ff549c1-4646-4ea4-879b-f598158280da": "07846725636"
   }
   ```

* **Response:**

   ```json
   {
     "success": true,
     "data": [
       {
         "value": "field_value_1",
         "field_id": "3c508a92-fb7d-4bb0-9694-5ba05b2d24cc",
         "form_id": "form_id_1",
         "entry_id": "entry_id_1",
         "deletedAt": null,
         "id": "field_data_id_1",
         "isActive": true,
         "createdAt": "2024-02-15T12:00:00Z",
         "updatedAt": "2024-02-15T12:30:00Z"
       },
       // ... more field data objects
     ]
   }
   ```

### 2. Get Form Field Data

* **Description:** Fetch field data based on form ID and optional filtering.

* **URL:** `/api/v1/field-data?form_id=62bac6ad-9a67-4711-bced-c362afd3de82&start_date=2024-02-12&end_date=2024-02-19&take=2&skip=0`

* **Method:** GET

* **Authentication:** Bearer Token

* **Query Parameters:**

   *  `form_id` (string, required): ID of the form.
   *  `start_date` (string, optional): Start date for data retrieval.
   *  `end_date` (string, optional): End date for data retrieval.
   *  `take` (integer, optional): Number of records to retrieve.
   *  `skip` (integer, optional): Number of records to skip.

* **Response:**

   ```json
   {
     "success": true,
     "data": { /* Field data objects, user info, metadata */} 
   }
   ```

### 3. Update Field Data

* **Description:** Update field data (including file updates).

* **URL:** `/api/v1/field-data/:id`

* **Method:** PATCH

* **Authentication:** Bearer Token

* **Request (Form Data):**

   *  `file`: File to update
   * `value`: Optional value to update the field data

* **Response:**

   ```json
   {
       "success": true,
       "data": {
           "id": "",
           "value": "",
           "field_id": "",
           // ... (other fields)
           "field": {
               "id": "",
               "label": "",
               // ... (other fields)
           } 
       }
   }
   ```

### 4. Delete Field Data

* **Description:** Delete a specific field data entry.

* **URL:** `/api/v1/field-data/:id`

* **Method:** DELETE

* **Authentication:** Bearer Token

* **Response:**

   * **Status Code:** 204 (No Content)
   * **Content Type:** application/json 

# Dashboard Stats Documentation

## Introduction

This documentation provides details for interacting with the API endpoints related to retrieving dashboard statistics.

## Endpoints

## 1. Institution

### Entries

- **Description:** Retrieves dashboard entries for a specific institution.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/institution/entries`
- **Request Parameters:**
  - `institution_id` (string, required): The unique identifier of the institution.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (integer): The number of entries for the institution.

### Projects

- **Description:** Retrieves projects associated with a specific institution.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/institution/projects`
- **Request Parameters:**
  - `institution_id` (string, required): The unique identifier of the institution.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (integer): The number of projects associated with the institution.

### Progress

- **Description:** Retrieves progress of a specific institution's dashboard.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/institution/progress`
- **Request Parameters:**
  - `institution_id` (string, required): The unique identifier of the institution.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (number): The progress value for the institution's dashboard.

### Users

- **Description:** Retrieves users associated with a specific institution.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/institution/users`
- **Request Parameters:**
  - `institution_id` (string, required): The unique identifier of the institution.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (number): The number of users associated with the institution.

## 2. Institution User

### Entries

- **Description:** Retrieves a user's entries for a specific period from the dashboard.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/user/entries`
- **Request Parameters:**
  - `user_id` (string, required): The unique identifier of the user.
  - `period` (string, required): The period for which the entries are requested.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (integer): The number of entries for the specified period.

### Projects

- **Description:** Retrieves projects associated with a specific user.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/user/projects`
- **Request Parameters:**
  - `user_id` (string, required): The unique identifier of the user.
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (integer): The number of projects associated with the user.

#### Super Admin

### Entries

- **Description:** Retrieves dashboard entries.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/entries`
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (object): Contains the dashboard entries.

### Projects

- **Description:** Retrieves a list of projects for the dashboard.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/projects`
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (number): Represents the number of projects.

### Institutions

- **Description:** Retrieves a list of institutions for the dashboard.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/institutions`
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (number): Represents the number of institutions.

### Progress

- **Description:** Retrieves the progress data for the dashboard.
- **HTTP Method:** GET
- **Endpoint:** `http://localhost:8080/api/v1/dashboard/progress`
- **Response:**
  - `success` (boolean): Indicates the success status of the request.
  - `data` (number): Represents the progress value for the dashboard.