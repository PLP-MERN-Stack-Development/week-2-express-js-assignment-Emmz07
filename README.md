# Express Products API

A RESTful API built with Express.js and MongoDB for managing products.

---

## 🚀 How to Run the Server

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/express-products-api.git
cd express-products-api
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create Environment File

Create a `.env` file based on the `.env.example` file:

```
MONGO_URI=mongodb+srv://emmz07:missallsunday07@stack00.czhas8d.mongodb.net/products_db
API_KEY=your-api-key
```

### 4. Start the Server

```bash
node index.js
```

Server will run on [http://localhost:3000](http://localhost:3000)

---

## 🔐 Authentication

All endpoints require an API key to be passed in the request headers:

```
x-api-key: your-secret-api-key
```

---

## 📚 API Endpoints

### `GET /api/products`

* Description: Get all products (supports pagination and filtering by category)
* Query Params: `category`, `page`, `limit`

#### Example:

```http
GET /api/products?page=1&limit=5&category=electronics
```

#### Response:

```json
{
  "total": 2,
  "page": 1,
  "products": [ 
{
  "name": "Smart Watch",
  "description": "Touchscreen fitness tracker",
  "price": 79.99,
  "category": "Electronics",
  "inStock": true
}

]
}
```

---

### `GET /api/products/:id`

* Description: Get a product by ID

#### Example:

```http
GET /api/products/6643ac8db123456789012345
```

#### Response:

```json
{
  "_id": "...",
  "name": "Product A",
  ...
}
```

---

### `GET /api/products/search?name=term`

* Description: Search products by name (case-insensitive)

#### Example:

```http
GET /api/products/search/
```

---

### `GET /api/products/stats`

* Description: Returns product count grouped by category

#### Response:

```json
[
  { "_id": "electronics", "count": 5 },
  { "_id": "books", "count": 3 }
]
```

---

### `POST /api/products`

* Description: Create a new product
* Body (JSON):

```json
{
  "name": "Product A",
  "description": "Description of product",
  "price": 99.99,
  "category": "electronics",
  "inStock": true
}
```

---

### `PUT /api/products/:id`

* Description: Update an existing product by ID

---

### `DELETE /api/products/:id`

* Description: Delete a product by ID

---

## Validation

* Required fields: `name`, `description`, `price`, `category`, `inStock`
* `price` must be a number
* `inStock` must be a boolean

---

## Technologies Used

* Express.js
* MongoDB (Mongoose)
* Morgan (logging)
* Dotenv

---

## 👨‍💻 Author

* Ojo Emmanuel Tiwalade - [GitHub](https://github.com/Emmz07)
