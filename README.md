# 🚀 REST API Testing Portfolio — Postman

This project demonstrates practical **REST API testing skills** using **Postman** and the **JSONPlaceholder** public REST API.

The project includes positive and negative API test scenarios, automated assertions, environment variables, dynamic data handling, and collection execution.

---

## 🎯 Project Objective

The goal of this project was to practice and demonstrate REST API testing from a **Junior QA Tester** perspective.

The tests focus on validating:

- HTTP methods
- HTTP status codes
- JSON response bodies
- Response structure
- Response headers
- Response time
- Positive and negative scenarios
- Dynamic variables
- API request and response data

---

## 🛠 Tools & Technologies

- Postman
- REST API
- JSON
- JavaScript
- JSONPlaceholder API
- GitHub

---

## 🔗 API Under Test

**JSONPlaceholder**

JSONPlaceholder is a free fake REST API used for testing and prototyping.

Base URL:

`https://jsonplaceholder.typicode.com`

> JSONPlaceholder simulates POST, PUT, PATCH and DELETE operations. Changes are not permanently persisted on the server.

---

## 📋 API Requests

The Postman collection contains the following requests:

| Method | Request | Purpose |
|---|---|---|
| GET | Get all users | Retrieve and validate the list of users |
| GET | Get user by ID | Retrieve a specific user using a dynamic ID |
| GET | Get non-existing user | Verify handling of a non-existing resource |
| POST | Create new post | Validate creation of a new resource |
| PUT | Update post | Validate full resource update |
| PATCH | Update post title | Validate partial resource update |
| DELETE | Delete post | Validate resource deletion |

---

## 🧪 Automated Tests

Postman scripts were used to automatically validate API responses.

The tests include:

- HTTP status code validation
- JSON response validation
- Required field validation
- Response data validation
- Response time validation
- Content-Type header validation
- Empty response validation
- Dynamic ID validation

Example assertion:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

---

## 🔄 Environment Variables

A Postman environment was created to avoid hardcoding configuration values.

Example:

```text
baseUrl = https://jsonplaceholder.typicode.com
```

Requests use the environment variable:

```text
{{baseUrl}}/users
```

A dynamic `userId` variable is also created from an API response and reused in another request.

Example flow:

```text
GET all users
      ↓
Save userId
      ↓
GET user by {{userId}}
```

Example script used to save the variable:

```javascript
const users = pm.response.json();

pm.environment.set("userId", users[0].id);
```

---

## ❌ Negative Testing

The collection includes a negative test for requesting a non-existing user.

Request:

```text
GET {{baseUrl}}/users/999
```

Expected result:

```text
HTTP 404 Not Found
```

The response body is also validated to confirm that an empty JSON object is returned.

Example assertion:

```javascript
pm.test("Status code is 404", function () {
    pm.response.to.have.status(404);
});

pm.test("Response body is empty object", function () {
    const jsonData = pm.response.json();

    pm.expect(jsonData).to.be.an("object");
    pm.expect(jsonData).to.be.empty;
});
```

---

## ▶️ Collection Runner

The complete collection was executed using the **Postman Collection Runner**.

The Collection Runner allows all API requests and automated assertions to be executed as a complete test suite.

### Test Execution Evidence

![Postman Collection Run](./screenshots/Postman_Collection_Run.png)

---

## 📁 Repository Structure

```text
api-testing-postman-portfolio/
│
├── README.md
│
├── postman/
│   ├── REST_API_Testing_Portfolio.postman_collection.json
│   └── JSONPlaceholder_Environment.postman_environment.json
│
└── screenshots/
    └── Postman_Collection_Run.png
```

---

## 📥 How to Run the Tests

1. Download or clone this repository.
2. Open Postman.
3. Import `REST_API_Testing_Portfolio.postman_collection.json`.
4. Import `JSONPlaceholder_Environment.postman_environment.json`.
5. Select `JSONPlaceholder Environment`.
6. Run individual API requests or execute the complete collection using Collection Runner.

---

## 💡 Skills Demonstrated

This project demonstrates practical knowledge of:

- REST API testing
- GET, POST, PUT, PATCH and DELETE methods
- HTTP status codes
- JSON request and response validation
- Postman automated assertions
- Positive and negative API testing
- Environment variables
- Dynamic variables
- Response headers validation
- Response time validation
- Collection Runner
- Basic JavaScript assertions
- GitHub project documentation

---

## 👤 Author

**Paweł Iwaszko**

Junior Manual QA Tester  
ISTQB® Certified Tester Foundation Level
