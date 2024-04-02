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
```