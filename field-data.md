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
