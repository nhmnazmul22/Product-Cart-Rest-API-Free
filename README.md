# Product Cart API Documentation
The Product Cart API allows users to manage their product listings, view product details, and manage their cart contents. This API provides a range of endpoints to handle authentication, product management, and cart management functionalities.
---
[![Run in Postman](https://run.pstmn.io/button.svg)](https://documenter.getpostman.com/view/9518923/2sAXqwaLEB)
---
#### 1. User Login
URL: POST /api/user-login
Request Body: 
```js
{
  "UserEmail":"user@example.com"
}
```
Response
```js
{
  "msg":"success",
  "data":"A 4 Digit OTP has been sent to your email address"
}
```
---

#### 2. Verify Login
URL: POST /api/verify-login
Request Body:

```js
{
  "UserEmail": "user@example.com",
  "OTP": "0000" // Use Default OTP 0000 always 
}
```
Response
```js
{
  "msg": "success",
  "data": "Your generated token here"
}

```
---

#### 3 Product Management
URL: GET /api/product-list
Response
```js
{
  "msg": "success",
  "data": [
        {
            "id": 1,
            "title": "MacBook Air M1 8/256GB",
            "short_des": "MacBook Air M1 8/256GB 13-inch Space Gray",
            "price": "94000",
            "discount": 0,
            "discount_price": "90000",
            "image": "https://cart-api.teamrabbil.com/image/product.jpeg",
            "stock": 1,
            "star": 5,
            "remark": "popular",
            "created_at": "2024-11-02T08:26:33.000000Z",
            "updated_at": "2024-11-02T08:26:33.000000Z"
        }
  ]
}
```
---

#### 4. Add Product to Cart
URL: GET /api/create-cart/:product_id
Headers: token: XXXXXXXXXXXXXXXXXXXXXXXXX
Response: 
```js
{
    "msg": "success",
        "data": {
        "id": 1,
            "user_id": "1",
            "product_id": "1"
    }
}
```
---

#### 4. Remove Product from Cart
URL: GET /api/remove-cart/:product_id
Headers: token: XXXXXXXXXXXXXXXXXXXXXXXXX
Response: 
```js
{
  "msg": "success",
  "data": 0
}

```
---

#### 5. List Cart Items
URL: GET /api/cart-list
Headers: token: XXXXXXXXXXXXXXXXXXXXXXXXX
Response:
```js
{
    "msg": "success",
    "data": [
        {
            "id": 1,
            "user_id": 1,
            "product_id": 1,
            "created_at": "2024-11-02T02:31:03.000000Z",
            "updated_at": "2024-11-02T02:31:03.000000Z",
            "product": {
                "id": 1,
                "title": "MacBook Air M1 8/256GB",
                "short_des": "MacBook Air M1 8/256GB 13-inch Space Gray",
                "price": "94000",
                "discount": 0,
                "discount_price": "90000",
                "image": "https://cart-api.teamrabbil.com/image/product.jpeg",
                "stock": 1,
                "star": 5,
                "remark": "popular",
                "created_at": "2024-11-02T08:26:33.000000Z",
                "updated_at": "2024-11-02T08:26:33.000000Z"
            }
        }
    ]
}
```
---