# Institution User API Documentation

## Introduction

This documentation provides details for interacting with the API endpoints related to managing institution users within a project.

## Endpoints

### 1. Create Project User

* **Description:**  Register a new institution user within a project.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/register/?project_id=dc42bc2d-bff2-4527-a134-0bc075bd20c6`

* **Method:** POST

* **Authentication:** Bearer Token

*  **Request Body (Form-Data):**

   *  `firstName`: (string) First name of the user.
   *  `lastName`: (string) Last name of the user.
   *  `phone`: (string) Phone number of the user.
   *  `email`: (string) Email address of the user.
   *  `file`: (file) User's image or profile picture.

* **Response:**

   * **Status Code:** 201 (Created)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "data": {
          "firstName": "",
          "lastName": "",
          "image_url": null,
          "phone": "",
          "email": "",
          "institution_id": "", 
          "otp": null,
          "deletedAt": null,
          "password": null,
          "id": "", 
          "isActive": true,
          "role": "",
          "createdAt": "",
          "updatedAt": "" 
        }
      }
      ```

### 2. Update Project User

* **Description:** Update an existing institution user's details.

* **URL:** `http://localhost:8080/api/v1/auth/institution-users/e36a7f8f-b7be-44d2-88e1-1fe15319db58`

* **Method:** PATCH

* **Authentication:** Bearer Token

* **Request Body (Form-Data):**

    *  `firstName`: (string) First name of the user.
    *  `lastName`: (string) Last name of the user.
    *  `phone`: (string) Phone number of the user.
    *  `email`: (string) Email address of the user.
    *  `file`: (file) User's image or profile picture.

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
          "success": true,
          "data": {
              "id": "",
              "firstName": "",
              "lastName": "",
              "email": "",
              "image_url": "",
              "institution_id": "",
              "phone": "",
              "isActive": true,
              "role": "",
              "createdAt": "",
              "updatedAt": "",
              "deletedAt": null,
              "otp": null,
              "institution": {
                  "id": "",
                  "name": "",
                  "logo": ""
              }
          }
      }
      ```

### 3. Institution User Auth (Login)

* **Description:**  Authenticate an institution user using their phone number.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/login`

* **Method:** POST

* **Authentication:** None

*  **Request Body (JSON):**

   ```json
   {
     "phone": "**********" 
   }
   ```

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "data": true 
      }
      ```

### 4. Institution User Verify OTP

* **Description:**  Verify the OTP (One-Time Password) for an institution user.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/otp/verify`

* **Method:** POST

* **Authentication:** None

*  **Request Body (JSON):**

   ```json
   {
     "otp": "123456",  
     "phone": "**********" 
   }
   ```

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "message": "OTP verified successfully", 
        "data": {
          "id": "", // User ID
          "firstName": "", 
          "lastName": "", 
          // ... other user details
          "token": "" // Authentication token
        } 
      }
      ```

### 5. Get Project Users

* **Description:** Retrieve a list of institution users associated with a project.

* **URL:** `http://localhost:8080/api/v1/auth/institution-users/?project_id=ddef0a52-e626-4311-a435-cad871f9e333&take=1&skip=0`

* **Method:** GET

* **Authentication:** Bearer Token

* **Query Parameters:**

  * `project_id` (string, required): ID of the project.
  * `take` (integer, optional): Number of records to retrieve.
  * `skip` (integer, optional): Number of records to skip.

* **Response**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json

   * **Response Body (Example):** 
     ```json
     {
       "success": true,
       "data": { /* User data, pagination details */ }
     }

### 6. Institution User Verify OTP

* **Description:**  Verify the OTP (One-Time Password) for an institution user.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/otp/verify`

* **Method:** POST

* **Authentication:** None

*  **Request Body (JSON):**

   ```json
   {
     "otp": "123456",  
     "phone": "0788478652" 
   }
   ```

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "message": "OTP verified successfully", 
        "data": {
          "id": "user_id", 
          "firstName": "John", 
          "lastName": "Doe",
          // ... other user details
          "token": "authentication_token" 
        } 
      }
      ```

### 7. Get Project Users

* **Description:** Retrieve a list of institution users associated with a project.

* **URL:** `http://localhost:8080/api/v1/auth/institution-users/?project_id=ddef0a52-e626-4311-a435-cad871f9e333&take=1&skip=0`

* **Method:** GET

* **Authentication:** Bearer Token

* **Query Parameters:**

  * `project_id` (string, required): ID of the project.
  * `take` (integer, optional): Number of records to retrieve.
  * `skip` (integer, optional): Number of records to skip.

* **Response**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json

   * **Response Body (Example):** 
     ```json
     {
       "success": true,
       "data": {
         "rows": [ /* Array of user objects */ ],
         "totalCount": 1, 
         "totalPages": 1, 
         "currentPage": 1 
       }
     }
     ``` 

### 8. Get User Details

* **Description:** Retrieve detailed information about a specific institution user.

* **URL:** `http://localhost:8080/api/v1/auth/institution-users/e36a7f8f-b7be-44d2-88e1-1fe15319db58`

* **Method:** GET

* **Authentication:** Bearer Token

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json

   * **Response Body (Example):** 
     ```json
     {
       "success": true,
       "data": {
         "id": "user_id",
         "firstName": "John",
         "lastName": "Doe",
         // ... other user details
         "institution": { /* Associated institution details */ } 
       }
     }
     ``` 

### 9. List User Projects

* **Description:** Retrieve a list of projects associated with an institution user.

* **URL:** `http://localhost:8080/api/v1/auth/institution-users/:id/projects`

* **Method:** GET

* **Authentication:** Bearer Token

* **Path Parameter:**
   * `:id` (string, required): ID of the institution user

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json

   * **Response Body (Example):** 
     ```json
     {
       "success": true,
       "data": [ /* Array of project objects */ ]
     }
     ``` 

### 10. Delete User

* **Description:**  Delete a specific institution user.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/:id`

* **Method:** DELETE

* **Authentication:** Bearer Token

* **Path Parameter:**
   * `:id` (string, required): ID of the institution user to be deleted

* **Response**

   * **Status Code:** 204 (No Content)
   * **Content Type:** text/xml 

### 11. Restore User

* **Description:**  Restore a previously deleted institution user.

* **URL:**  `http://localhost:8080/api/v1/auth/institution-users/restore`

* **Method:** PATCH

* **Authentication:** Bearer Token

*  **Request Body (JSON):**

   ```json
   {
     "phone": "0788478652"
   }
   ```

* **Response:**

   * **Status Code:** 200 (OK)
   * **Content Type:** application/json 

   * **Response Body (Example):**

      ```json
      {
        "success": true,
        "data": {
          // ... restored user details 
        } 
      }
      ```