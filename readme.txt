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
  "customer_id": "641c4f20cea2a5129f5f9820",
  "restaurant_id": "641abf98e09e75eb5215d5bf",
  "items": [
    {
      "food_id": "641c4cb8cea2a5129f5f980d",
      "name": "Greek Chesse Stuffed Pizza",
      "quantity": 3,
      "price": 57.00
    },
        {
      "food_id": "641a8ac771a93b2eb921d5b2",
      "name": "Greek Chesse Stuffed Sandwitch",
      "quantity": 2,
      "price": 37.00
    }
    ],
  "status": "Pending",
  "total": 80.00,
  "deliveryAddress": "23BC Main Land, CA"
}
NOTE: Customer's Bearer Token needs to be sent along with request inorder to order food


GET: http://localhost:5001/api/orders/customer/:customerId
NOTE: Customer's Bearer Token needs to be sent along with request inorder to view all the orders of a specific Customer


GET: http://localhost:5001/api/orders/:orderId
NOTE: Customer's Bearer Token needs to be sent along with request inorder to view the specific order made by specific Customer

PUT: http://localhost:5001/api/orders/:orderId
NOTE: Customer's Bearer Token needs to be sent along with request inorder to update the specific order made by specific Customer

DELETE: http://localhost:5001/api/orders/:orderId
NOTE: Customer's Bearer Token needs to be sent along with request inorder to delete the specific order made by specific Customer
