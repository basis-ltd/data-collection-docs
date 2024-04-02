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
```