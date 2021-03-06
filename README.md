# Postman
Repository for presentation in Software Engineering

## Download or use web app
https://www.postman.com/

## used test API
https://simple-books-api.glitch.me/

## Documentation of written Tests in presentation
https://documenter.getpostman.com/view/15635439/TzXwFe7K


### Status ###

GET `/status`

Returns the status of the API.


### List of books ###

GET `/books`

Returns a list of books.


### Get a single book ###

GET `/books/:bookId`

Retrieve detailed information about a book.


### Submit an order ###

POST `/orders`

Allows you to submit a new order. Requires authentication.

The request body needs to be in JSON format and include the following properties:

 - `bookId` - Integer - Required
 - `customerName` - String - Required

Example
```
POST /orders/
Authorization: Bearer <YOUR TOKEN>

{
  "bookId": 1,
  "customerName": "John"
}
```

The response body will contain the access token.


### Get all orders ###

GET `/orders`

Allows you to view all orders. Requires authentication.


### Update an order ###

PATCH `/orders/:orderId`

Update an existing order. Requires authentication.

The request body needs to be in JSON format and allows you to update the following properties:

 - `customerName` - String

 Example
```
PATCH /orders/PF6MflPDcuhWobZcgmJy5
Authorization: Bearer <YOUR TOKEN>

{
  "customerName": "John"
}
```


### Delete an order ###

DELETE `/orders/:orderId`

Delete an existing order. Requires authentication.

The request body needs to be empty.

 Example
```
DELETE /orders/PF6MflPDcuhWobZcgmJy5
Authorization: Bearer <YOUR TOKEN>
```

## API Authentication ##

To submit or view an order, you need to register your API client.

POST `/api-clients/`

The request body needs to be in JSON format and include the following properties:

 - `clientName` - String
 - `clientEmail` - String

 Example

 ```
 {
    "clientName": "Alina",
    "clientEmail": "alina@example.com"
}
 ```

The response body will contain the access token.
