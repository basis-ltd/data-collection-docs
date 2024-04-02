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
