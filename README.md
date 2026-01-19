
# 🧪 Postman RESTful Booker API Test Suite

This repository contains a **Postman-based API test suite** for the **Restful Booker** service.
All assets are shared as **JSON files** so they can be easily imported and executed in Postman.

---

## 📁 Project Contents

The project is delivered with the following files:

```
.
├── collection.json        # Postman collection (requests + tests)
├── environment.json       # Postman environment variables
├── test-results.json      # Collection runner results
└── README.md              # Project documentation
```

---

## 🔐 Authentication Strategy

This project uses **Token-Based Authentication**.

### Flow:
1. A token is generated using the `/auth` endpoint.
2. The token is stored as an **environment variable**.
3. Protected endpoints (`PUT`, `PATCH`, `DELETE`) send the token via:
   ```
   Cookie: token={{token}}
   ```

This mirrors real-world API security practices and avoids hardcoded credentials.

---

## ▶️ Running the Collection in Postman

### 1️⃣ Import Files
- Open **Postman**
- Click **Import**
- Import:
  - `collection.json`
  - `environment.json`

### 2️⃣ Select Environment
- Choose the imported **environment** from the top-right dropdown
- Verify `baseUrl` is correctly set

### 3️⃣ Run Collection
- Open the collection
- Click the **three dots (⋮)**
- Select **Run collection**
- Click **Run** 🚀

All requests execute sequentially using shared variables.

---

## ✅ Testing & Validation

### ✔ Status Code Assertions
Each request validates expected HTTP status codes.

### ✔ JSON Schema Validation
Responses are validated using Postman’s built-in `jsonSchema` matcher.

- Ensures response structure consistency
- Detects breaking contract changes
- Keeps test scripts clean and readable

Schemas are stored as **collection variables** and reused across requests.

---

## 🧠 Notes

- No hardcoded credentials or IDs
- Token generated dynamically
- Environment-driven execution
- Designed for collection runner usage

---


