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