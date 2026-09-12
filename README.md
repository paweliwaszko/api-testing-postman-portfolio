# 🚀 REST API Testing Portfolio — Postman

This project demonstrates practical REST API testing skills using **Postman** and the **JSONPlaceholder** public REST API.

The project includes positive and negative API test scenarios, automated assertions, environment variables, dynamic data handling, and collection execution.

---

## 🎯 Project Objective

The goal of this project was to practice and demonstrate REST API testing from a Junior QA perspective.

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
