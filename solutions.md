###### _Completed. Joseph P. Pasaoa_

# Todos API
**root:** https://fsw62-todos-api.herokuapp.com/api


## Resources
* users
* todos

## Endpoints

#### Users
| Method | Endpoint           | What does this do? |
|--------|--------------------|--------------------|
| `GET`  | `/users`           | returns list of all user objects|
| `GET`  | `/users/<username>`| returns individual user object|
| `POST`  | `/users/signup`   | enables method to create user object|


_Fill in the blanks above_ :arrow_up: 

#### Todos
| Method   | Endpoint           | Possible Query Params| What does this do?  |
|----------|--------------------|--------------------|-----------------------|
| `GET`    | `/todos`           | `owner=<username>`, `completed=<true/false>` | returns list of all todos with a queried user|
| `POST`   | `/todos`           || enables method to create todo task item|
| `GET`    | `/todos/<todo.id>` || returns task item info|
| `PUT`    | `/todos/<todo.id>` || enables method to update entire todo task item|
| `PATCH`  | `/todos/<todo.id>` || enables method to partially update todo task item|
| `DELETE` | `/todos/<todo.id>` || removes specified todo task item from system|

_Fill in the blanks above_ :arrow_up: 

***

## Task ONE
Try out all the requests that are possible with this API. For all the possible requests Create a list like the following.
Separate requests by a long line of underscores.

> **SAMPLE**
>    * **Request**: METHOD - ENDPOINT
>    * **Body** (if applicable POST/PUT/PATCH)
>    ```json
>      {
>        "owner": "alejo4373",
>        "text": "1st Todo"
>      }
>    ```
>    * **Response**:
>    ```json
>    {
>      "userId": 1,
>      "id": 1,
>      "title": "delectus aut autem",
>      "completed": false
>    }
>    ```
>    * **What does it do?**: EXPLAIN WHAT THE REQUEST DID/DO IN PLAIN ENGLISH
---
---
### 1. **Request**: GET - /users

**Body**: (n/a)

**Response**:

```json
{
  "id": 1,
  "username": "alejo4373"
},
{
  "id": 2,
  "username": "JRJRocks"
},
{
  "id": 3,
  "username": "Mike923"
},
{
  "id": 4,
  "username": "3Chainz"
}
}
```
**What does it do?**: Returns a listing of all the user objects in the system

---
### 2. **Request**: GET - /users/\<username>

**Body**: (n/a)

**Response**:

```json
{
  "id": 1,
  "username": "alejo4373"
}
```
**What does it do?**: Returns a single specified user object

---
### 3. **Request**: POST - /users/signup

**Body**:

```json
{
  "username": "the real not alejo4373"
}
```
**Response**:

```json
{
  "user": {
    "id": 25,
    "username": "the real not alejo4373"
  },
  "msg": "User created"
},
```
**What does it do?**: Creates a new user object

---
### 4. **Request**: GET - /todos

**Body**: (n/a)

**Response**:

```json
[
  {
    "id": "ecf57050",
    "owner": "AnimalCrackerEater",
    "text": "Leave Crackers on the sofa",
    "completed": false
  },
  {
    "id": "33a3ebd0",
    "owner": "jenesh",
    "text": "spread radical candor",
    "completed": false
  },
  {
    "id": "0d0fce60",
    "owner": "kitkatjewels",
    "text": "I am sleepy!",
    "completed": false
  }
]
```
**What does it do?**: Gives back an array of all the todo tasks in the system

---
### 5. **Request**: GET - /todos?owner=the real not alejo4373

**Body**: (n/a)

**Response**:

```json
[
  {
    "id": "188b0300",
    "owner": "the real not alejo4373",
    "text": "rip out hair after multiple GET errors",
    "completed": false
  },
  {
    "id": "2f77d8e0",
    "owner": "the real not alejo4373",
    "text": "look over at neighbor's screen to see if they're anywhere better in the lab",
    "completed": false
  },
  {
    "id": "fd3a5dd0",
    "owner": "the real not alejo4373",
    "text": "stare blankly at Postman for minutes",
    "completed": true
  },
  {
    "id": "7b453650",
    "owner": "the real not alejo4373",
    "text": "wish i had the real alejo4373's knowledge",
    "completed": false
  },
  {
    "id": "8feb0260",
    "owner": "the real not alejo4373",
    "text": "find edible food. profit!!!",
    "completed": false
  }
]
```
**What does it do?**: Gives back an array of all the todo tasks owned by specified user

---
### 6. **Request**: GET - /todos?owner=the real not alejo4373&completed=true

**Body**: (n/a)

**Response**:

```json
[
  {
    "id": "fd3a5dd0",
    "owner": "the real not alejo4373",
    "text": "stare blankly at Postman for minutes",
    "completed": true
  }
]
```
**What does it do?**: Gives back an array of all todo tasks satisfying all queries, here specified owner and if completed

---
### 7. **Request**: POST - /todos

**Body**:

```json
{
  "owner": "the real not alejo4373",
  "text": "find edible food. profit!!!"
}
```
**Response**:

```json
{
  "id": "8feb0260",
  "owner": "the real not alejo4373",
  "text": "find edible food. profit!!!",
  "completed": false
}
```
**What does it do?**: Creates new todo task with posted data entered

---
### 8. **Request**: GET - /todos/188b0300

**Body**: (n/a)

**Response**:

```json
{
  "id": "188b0300",
  "owner": "the real not alejo4373",
  "text": "rip out hair after multiple GET errors",
  "completed": false
}
```
**What does it do?**: Fetches single specified todo task

---
### 9. **Request**: PUT - /todos/fd3a5dd0

**Body**:

```json
{
  "owner": "the real not alejo4373",
  "text": "stare blankly at Postman for HOURS",
  "completed": true
}
```
**Response**:

```json
{
  "id": "fd3a5dd0",
  "owner": "the real not alejo4373",
  "text": "stare blankly at Postman for HOURS",
  "completed": true
}
```
**What does it do?**: Updates entire todo task item accordingly

---
### 10. **Request**: PATCH - /todos/7b453650

**Body**:

```json
{
  "completed": true
}
```
**Response**:

```json
{
  "id": "7b453650",
  "owner": "the real not alejo4373",
  "text": "wish i had the real alejo4373's knowledge",
  "completed": true
}
```
**What does it do?**: Updates partially a todo task item

---
### 11. **Request**: DELETE - /todos/8f641390

**Body**: (n/a)

**Response**:

```json
{
  "id": "8f641390",
  "owner": "AnimalCrackerEater",
  "text": "Create item under  another user",
  "completed": false
}
```
**What does it do?**: Removes the specified todo task from the system

---
<!---
**Request**: METHOD - ENDPOINT

**Body** (if applicable POST/PUT/PATCH)

```json
  {
  }
```
**Response**:

```json
{
}
```
**What does it do?**: EXPLAIN WHAT THE REQUEST DID/DO IN PLAIN ENGLISH
--->
---


## TASK TWO

Find as much status codes as possible. I will tell you how many there are by the end.

#### **_6 FOUND_**

**_200 OK_**
```
GET - https://fsw62-todos-api.herokuapp.com/api/todos?owner=the real not alejo4373
```

**_201 Created_**
```
POST - https://fsw62-todos-api.herokuapp.com/api/users/signup
{ "username": "test3" }

=> { "msg": "User created" }
```

**_400 Bad Request_**
```
VIEW - https://fsw62-todos-api.herokuapp.com/api/users
```

**_404 Not Found_**
```
DELETE - https://fsw62-todos-api.herokuapp.com/api/users/"not alejo4373"
```

**_409 Conflict_**
```
POST - https://fsw62-todos-api.herokuapp.com/api/users/signup
{ "username": "test" }

=> { "msg": "Username not available. Please try a different one." }
```

**_500 Internal Server Error_**
```
PATCH - https://fsw62-todos-api.herokuapp.com/api/todos/7b453650
{ "comple": true }

=> { "errStack": "Error: Cannot generate an UPDATE without any columns. [. . .] }"
```

***
***

## BONUSES
1. Take a look at the next lesson. To learn how to make make network requests with Javascript
Since you previously had build a simple Todos APP with HTML try to connect that app to this
API so that todos you enter in the page are save to the API. Marking a todo as complete or uncompleted
should work.
2. Find the easter egg.

#### **_FOUND: Sept 15, 2019 3:33PM_**
```
POST - https://fsw62-todos-api.herokuapp.com/6
{ "username": "the real not alejo4373" }
```

![Proof Screencap](./Screen-Shot-2019-09-15-at-3.33.29-PM.png)