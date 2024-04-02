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
