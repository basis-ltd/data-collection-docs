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