Category:
=========
POST: localhost:5001/api/categories
{
  "name": "Sandwitches"
}

GET: localhost:5001/api/categories

GET: localhost:5001/api/categories/:categoryId

PUT: localhost:5001/api/categories/:id
{
  "name": "Pizza"
}

DELETE: localhost:5001/api/categories/:id
===============================================================


Food:
=========

POST: http://localhost:5001/api/foods/
{
  "title": "Greek Chesse Stuffed Sandwitch",
  "price": 17,
  "serves": 2,
  "desc": "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries.",
  "category_id": "641c4ae3cea2a5129f5f9802"
}

GET: http://localhost:5001/api/foods/

GET: http://localhost:5001/api/foods/category/:category_id

GET: localhost:5001/api/foods/:foodId

PUT: localhost:5001/api/foods/:foodId

DELETE: localhost:5001/api/foods/:foodId

===============================================================

Customer:
=========

POST: http://localhost:5001/api/customers/register
{
  "username": "Rick",
  "email": "xyz@abc.com",
  "password": "12345",
  "address": "11-ML, NY",
  "phone": "404 344 1111"
}

POST: http://localhost:5001/api/customers/login
{
  "email": "xyz@abc.com",
  "password": "12345"
}

Note: Customer will get a token when they login, that can be sent when they want to view customer profile, order items, update/delete items

GET: http://localhost:5001/api/customers/
NOTE: Customer's Bearer Token needs to be sent along with request inorder to view the Customer info
===============================================================

Restaurants:
===========
POST: localhost:5001/api/restaurants
{
  "name": "Mike Foods",
  "desc": "Fast Foods, Sea Foods",
  "location": "A165 Main Land NY",
  "menu": [
    "6416a287da6ccac47f1dc0d8",
    "641a8ac771a93b2eb921d5b2"
    ]
 }

GET: localhost:5001/api/restaurants

GET: localhost:5001/api/restaurants/:restaurantId

PUT: localhost:5001/api/restaurants/:restaurantId
{
  "name": "Rick's Kitchen",
  "desc": "Fast Foods, Sea Foods",
  "location": "C165 Main Land NY",
  "menu": [
    "6416a287da6ccac47f1dc0d8",
    "641c4cb8cea2a5129f5f980d",
    "641a8ac771a93b2eb921d5b2"
    ]
 }

DELETE: localhost:5001/api/restaurants/:restaurantId
===============================================================


Order:
=======

POST: http://localhost:5001/api/orders
{
  "user_id": "6412da89e5eec07910ebf31d",
  "title": "",
  "qty": 3,
  "size": 7,
  "color": "Black",
  "product_id": "6412cc48e5eec07910ebf310",
  "category_id": "641294cae5eec07910ebf304"
}
NOTE: User's Bearer Token needs to be sent along with request inorder to order product


GET: http://localhost:5001/api/orders/user
NOTE: User's Bearer Token needs to be sent along with request inorder to view all the orders of a specific User


GET: http://localhost:5001/api/orders/:orderId
NOTE: User's Bearer Token needs to be sent along with request inorder to view the specific order made by specific User

PUT: http://localhost:5001/api/orders/:orderId
NOTE: User's Bearer Token needs to be sent along with request inorder to update the specific order made by specific User

DELETE: http://localhost:5001/api/orders/:orderId
NOTE: User's Bearer Token needs to be sent along with request inorder to delete the specific order made by specific User
