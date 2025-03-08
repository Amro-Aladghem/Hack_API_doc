# Base URL for the API

The **Base URL** for the API is:
https://hackathoonproject-g4hkagbff0gygshm.germanywestcentral-01.azurewebsites.net/api/v1

You can use this base URL to send requests to the API endpoints.

# Error Object :

```json
{
  "message": "The error message is here!"
}
```

# API Routes for User

The following are the available routes for managing users:

### 1. **test api**

- **Endpoint**: `GET /user/test`
- **Header**: `nothing null`
- **Body**: `nothing null`

### 2. **Login User**

- **Endpoint**: `Post /user/login`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**:

  - `email`
  - `password`

- **Example Response (JSON)**:
  ```json
  {
    "user": {
      "userId": 2,
      "firstName": "Ali",
      "lastName": "Mhody"
    },
    "token": "f46ec358-4138-4e61-947d-068fa1d36f95"
  }
  ```

### 3. **Register User**

- **Endpoint**: `Post /user/register`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**:

  - `Email`
  - `Password`
  - `FirstName`
  - `LastName`
  - `Age`: `not required  يمكنك عدم ارساله  type:int`
  - `DateOfBirth`: `not required  يمكنك عدم ارساله  type:Date`
  - `Phone`: `not required  يمكنك عدم ارساله  type:string`

- **Example Response (JSON)**:
  ```json
  {
    "user": {
      "userId": 2,
      "firstName": "Ali",
      "lastName": "Mhody"
    },
    "token": "f46ec358-4138-4e61-947d-068fa1d36f95"
  }
  ```
