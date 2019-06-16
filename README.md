# fancy-todo


#Todo:
| Routes | Method | Headers | Request Body | Response Success | Response Error | Description|
|-----------------------------------|-----|----|----------------------------------|------------------|---------------------|------------------------------------------------------------------------------|
| `/api/todo/read/all/`| GET | token **Required**| -| ```[{"_id":"5d062da5bf24510b82500a1d", "name": "Coba", "description": "asfeqfwrg", "status": "On Going","dueDate": "2019-06-18T00:00:00.000Z","userEmail": "ninjahatori@gmail.com","__v": 0}]```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Get all the user's todos|
| `/api/todo/read/one/:todoId`| GET | token **Required**| -| ```[{"_id":"5d062da5bf24510b82500a1d", "name": "Coba", "description": "asfeqfwrg", "status": "On Going","dueDate": "2019-06-18T00:00:00.000Z","userEmail": "ninjahatori@gmail.com","__v": 0}]```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Get one todo based on its id|
| `/api/todo/create`| POST | token **Required**| name:String <br> description:String <br> status:String <br> dueDate:Date <br> userEmail:String <br>| ```{"_id":"5d062da5bf24510b82500a1d", "name": "Coba", "description": "asfeqfwrg", "status": "On Going","dueDate": "2019-06-18T00:00:00.000Z","userEmail": "ninjahatori@gmail.com","__v": 0}```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Add a todo into database|
| `/api/todo/update/:todoId`| PATCH | token **Required**| name:String <br> description:String <br> status:String <br> dueDate:Date <br> userEmail:String <br>| ```{"n": 1, "nModified": 1, "ok": 1}```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Edit a todo|
| `/api/todo/delete/:todoId`| DELETE | token **Required**| - | ```{"n": 1, "ok": 1, "deletedCount": 1}```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Delete a todo|

<br>
#User:
| Routes | Method | Headers | Request Body | Response Success | Response Error | Description|
|-----------------------------------|-----|----|----------------------------------|------------------|---------------------|------------------------------------------------------------------------------|
| `/user/register`| POST | - | firstName: String <br> lastName: String <br> email: String <br> password: String| ```{"_id": "5d06521e6961ec126ed934f3", "firstName": "Uzumaki", "lastName": "Nobita", "email": "uzumakinobita@gmail.com", "password": "$2a$10$88woarIgPqug02EjVAAnI.mCtzvperV.oA8HV2XSPWjnsclDraA9i", "__v": 0}```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | Register User|
| `/user/login`| POST | - | email: String <br> password: String| ```"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI1ZDA1MDI3YzZjNWQ2NDVkOTY5MDRkYzgiLCJlbWFpbCI6Im5pbmphaGF0b3JpQGdtYWlsLmNvbSIsImlhdCI6MTU2MDY5NTQyMH0.VcohCGQWZEpblb7ckovI9lsqgbC67q8b0LJacLpsgq0"```| 400 (Invalid Token)<br> 401 (Please login first) <br> 404 (User not found) <br> 500 (Internal Server Error) | User Login Validation |