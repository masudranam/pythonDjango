# Django Project Initialization

#1. Create a virtual environment:
    ```bash
    python -m venv venv
    ```

2. Activate the virtual environment:
    ```bash
    source venv/bin/activate
    ```

3. Install Django:
    ```bash
    pip install django
    ```

4. Save the installed packages to `requirements.txt`:
    ```bash
    pip freeze > requirements.txt
    ```

5. Start a new Django project:
    ```bash
    django-admin startproject <project-name>
    ```


# API Design

## Create Product
- **Method:** POST
- **Endpoint:** `api/v1/products`
- **Authentication:** Basic or Bearer Token
- **Request Body:**
    ```json
    {
        "name": "product_name",
        "price": "price"
    }
    ```
- **Response:**
  - 1xx: Informational responses
  - 2xx: Successful responses
    - 201: Product created successfully
  - 4xx: Client error responses
    - 400: Bad request (invalid input)
    - 401: Unauthorized
  - 5xx: Server error responses
    - 500: Internal server error

---

## Get All Products
- **Method:** GET
- **Endpoint:** `api/v1/products`
- **Authentication:** Basic or Bearer Token
- **Request Body:** None
- **Response:**
    ```json
    {
        "id": "_id"
    }
    ```
  - 1xx: Informational responses
  - 2xx: Successful responses
    - 200: OK (list of products)
  - 4xx: Client error responses
    - 401: Unauthorized
  - 5xx: Server error responses
    - 500: Internal server error

---

## Get Product by ID
- **Method:** GET
- **Endpoint:** `api/v1/products/{id}`
- **Authentication:** Basic or Bearer Token
- **Request Body:** None
- **Response:**
    ```json
    {
        "id": "_id"
    }
    ```
  - 200: OK (product found)
  - 401: Unauthorized
  - 404: Not found
  - 500: Server error

---

## Update Product
- **Method:** PUT or PATCH
- **Endpoint:** `api/v1/products`
- **Authentication:** Basic or Bearer Token
- **Request Body:**
  - PUT: Full object
  - PATCH: Partial object
- **Response:**
    ```json
    {
        "id": "_id"
    }
    ```
  - 200: OK (product updated)
  - 401: Unauthorized
  - 404: Not found
  - 500: Server error

---

## Delete Product
- **Method:** DELETE
- **Endpoint:** `api/v1/products/{id}`
- **Authentication:** Basic or Bearer Token
- **Request Body:** None
- **Response:**
    ```json
    {
        "delete": "success"
    }
    ```
  - 200: OK (product deleted)
  - 401: Unauthorized
  - 404: Not found
  - 500: Server error
