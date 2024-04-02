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
