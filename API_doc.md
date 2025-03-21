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

# API Routes for Chat

The following are the available routes for managing Chat:

### 2. **Math Chat**

- **Endpoint**: `Post /bot/math`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**:

  - `SessionId`:`في أول بداية المحادثة ارسل  قيمته فارغة , ثم بعد الرد الأول عليك ارسال الرقم المرسل`
  - `UserId`:`يمكنك عدم ارساله بتاتا , هذا فقط في حال المستخدم مسجل دخوله لا يهم اذا ارسلته `
  - `IsFirstTime`:`type:bool في أول رسالة مع البوت يجب ان تكون قيمته true`
  - `Message`:`مسج المستخدم`
  - `Image`:`الصورة , في حال ارسال المستخدم صورة ارسلها اذا لم يكن هنالك صورة ارسل قيمتها null `

- **Example Response (JSON)**:

  ```json
  {
    "responseMessageDTO": {
      "sessionId": 24,
      "userId": null,
      "message": "تمام، بما أنك في المرحلة المتوسطة، سأشرح لك طريقة حل هذا النظام من المعادلات بطريقة مبسطة وخطوة بخطوة.\n\n**النظام المعطى هو:**\n\n1.  `y = 2x + 1`\n2.  `5x + 6 = 2y`\n3.  `3x + 4y = 12`\n\n**الخطوة 1: استخدام المعادلة الأولى للتعويض في المعادلة الثانية**\n\n*   لدينا `y = 2x + 1`. سنعوض بهذه القيمة في المعادلة الثانية.\n*   المعادلة الثانية هي `5x + 6 = 2y`.\n*   نعوض `y` بـ `2x + 1`:\n    `5x + 6 = 2(2x + 1)`\n\n**الخطوة 2: حل المعادلة الجديدة لإيجاد قيمة `x`**\n\n*   نوزع الـ 2 في الطرف الأيمن:\n    `5x + 6 = 4x + 2`\n*   نطرح `4x` من الطرفين:\n    `5x - 4x + 6 = 4x - 4x + 2`\n    `x + 6 = 2`\n*   نطرح 6 من الطرفين:\n    `x + 6 - 6 = 2 - 6`\n    `x = -4`\n\n**الخطوة 3: إيجاد قيمة `y` باستخدام قيمة `x`**\n\n*"
    }
  }
  ```

  ### 3. **Physics Chat**

- **Endpoint**: `Post /bot/physics`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**: -`ينطبق عليه كل ما ينطبق على math`

  ### 4. **Chemistry Chat**

- **Endpoint**: `Post /bot/chemistry`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**: -`ينطبق عليه كل ما ينطبق على math`

  ### 5. **History Chat**

- **Endpoint**: `Post /bot/history`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**: -`ينطبق عليه كل ما ينطبق على math`

# The following are the available routes for managing tools:

### 1. **Time Table maker**

- **Endpoint**: `Post /tools/timetable`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**:

  - `DateOfStart`
  - `TimeOfStart`
  - `DateOfEnd`
  - `TimeOfEnd` -`file`

- **Example Response (JSON)**:

  ```json
  {
    "htmlCode": ""
  }
  ```

  ### 2. **Quiz maker**

- **Endpoint**: `Post /tools/quizmaker`
- **Header**: `Content-Type: multipart/form-data`
- **Form Data**:

  - `NumberOfQuestion` -`file`:

- **Example Response (JSON)**:

  ```json
  {
    "questions": [
      {
        "questionId": 1,
        "questionName": "What is the goal of statistics, according to the lecture?",
        "choices": [
          {
            "id": 1,
            "choiceText": "To collect data from college students"
          },
          {
            "id": 2,
            "choiceText": "To learn the distribution of X"
          },
          {
            "id": 3,
            "choiceText": "To make no assumptions about the pmf"
          },
          {
            "id": 4,
            "choiceText": "To learn the parameter of the Poiss(λ) distribution"
          }
        ],
        "rightChoiceId": 2
      },
      {
        "questionId": 2,
        "questionName": "What is a statistical model associated with a statistical experiment?",
        "choices": [
          {
            "id": 1,
            "choiceText": "A single probability measure on E"
          },
          {
            "id": 2,
            "choiceText": "A parameter set Θ"
          },
          {
            "id": 3,
            "choiceText": "A pair (E, (IPθ)θ∈Θ)"
          },
          {
            "id": 4,
            "choiceText": "The sample space E"
          }
        ],
        "rightChoiceId": 3
      }
    ]
  }
  ```
