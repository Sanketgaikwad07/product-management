

# Product Management REST API (Spring Boot)


##  Features

* Create a new product
* Get all products
* Get product by ID
* Update product by ID
* Delete product by ID
* RESTful API structure
* Uses `ResponseEntity` for proper HTTP responses

---

## 🛠️ Tech Stack

* Java 17+
* Spring Boot
* Spring Web
* Spring Data JPA
* Hibernate
* MySQL / H2 Database
* Maven

---

## 📁 Project Structure

```
com.book.demo
│
├── Controller
│   └── ProductController.java
│
├── Entity
│   └── Product.java
│
├── Services
│   ├── ProductService.java
│   └── ProductServiceImpl.java
│
├── Repository
│   └── ProductRepository.java
│
└── DemoApplication.java
```

---

## 📌 API Endpoints

### ➕ Create Product

```
POST /api/v1/product
```

**Request Body:**

```json
{
  "name": "Book",
  "price": 499,
  "description": "Spring Boot Book"
}
```

---

### 📦 Get All Products

```
GET /api/v1/products
```

---

### 🔍 Get Product by ID

```
GET /api/v1/products/{id}
```

---

### ✏️ Update Product

```
PUT /api/v1/products/{id}
```

**Request Body:**

```json
{
  "name": "Updated Book",
  "price": 599,
  "description": "Updated Description"
}
```

---

### ❌ Delete Product

```
DELETE /api/v1/products/{id}
```

---

## ⚙️ Configuration

### `application.properties`

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/product_db
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
```


---

## ▶️ How to Run

1. Clone the repository

   ```bash
   git clone https://github.com/Sanketgaikwad-7/product-api.git
   ```

2. Navigate to the project

   ```bash
   cd product-api
   ```

3. Run the application

   ```bash
   mvn spring-boot:run
   ```

4. API will be available at

   ```
   http://localhost:8080/api/v1
   ```

---

## 🧪 Testing

You can test the APIs using:

* Postman
* Swagger (if enabled)
* curl

---

## 📌 Example Controller

```java
@RestController
@RequestMapping("/api/v1")
public class ProductController {

    @PostMapping("/product")
    public ResponseEntity<Product> saveProduct(@RequestBody Product product) {
        return ResponseEntity.ok(productService.saveProduct(product));
    }
}
```



