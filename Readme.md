
# Task Manager REST API

A production-ready Task Management REST API built with **Django Rest Framework**, featuring **JWT authentication**, **secure user-based CRUD operations**, **filtering**, and **pagination**.

This project is designed as a backend-focused portfolio project, showcasing real-world API design and authentication practices.


## 🚀 Features

- User registration
- JWT authentication (access & refresh tokens)
- Secure, user-specific task management
- Create, read, update, delete (CRUD) tasks
- Task status filtering (`pending` / `completed`)
- Pagination for large datasets
- Clean RESTful API design

---

## 🛠 Tech Stack

- Python
- Django
- Django Rest Framework
- Simple JWT
- SQLite (development)


## 📂 Project Structure



Task-Manager-API/ 
├── core/
│   ├── settings.py
│   └── urls.py
├── users/
│   ├── serializers.py
│   ├── views.py
│   └── urls.py
├── tasks/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   └── urls.py
├── manage.py
├── requirements.txt
└── README.md

````

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository
```bash
git clone https://github.com/bayodelefaith/Task-Manager-API.git
cd Task-Manager-API
````

---

### 2️⃣ Create and activate virtual environment

**Windows (Git Bash)**

```bash
>> python -m venv venv
>> source venv/Scripts/activate
```

---

### 3️⃣ Install dependencies

```bash
>> pip install -r requirements.txt
```

---

### 4️⃣ Run migrations

```bash
>> python manage.py makemigrations
>> python manage.py migrate
```

---

### 5️⃣ Start development server

```bash
>> python manage.py runserver
```

Server will run at:

```
http://127.0.0.1:8000/
```

---

## 🔐 Authentication Flow (JWT)

### Register User

```
POST /api/users/register/
```

Request body:

```json
{
  "username": "exampleuser",
  "email": "user@example.com",
  "password": "strongpassword123"
}
```
![JWT Login](/screenshots/registration.png)
---

### Login (Get Tokens)

```
POST /api/token/
```

```json
{
  "username": "exampleuser",
  "password": "strongpassword123"
}
```

Response:

```json
{
  "refresh": "refresh_token",
  "access": "access_token"
}
```
![JWT Login](/screenshots/Jwt-login.png)
---

### Authorization Header

Use the **access token** for all protected endpoints:

```
Authorization: Bearer <access_token>
```

---

## 📝 Task Endpoints

### Create Task

```
POST /api/tasks/
```

```json
{
  "title": "Build Django API",
  "description": "Implement authentication and CRUD"
}

```
![Create Task](/screenshots/Create-task.png)

---

### List Tasks

```
GET /api/tasks/
```

---

### Retrieve / Update / Delete Task

```
GET    /api/tasks/<id>/
PUT    /api/tasks/<id>/
DELETE /api/tasks/<id>/
```

---

## 🔍 Filtering

Filter tasks by status:

```
GET /api/tasks/?status=pending
GET /api/tasks/?status=completed
```

---

## 📄 Pagination

Paginated responses are enabled by default:

```
GET /api/tasks/?page=2
```

Response format:

```json
{
  "count": 12,
  "next": "http://127.0.0.1:8000/api/tasks/?page=2",
  "previous": null,
  "results": []
}
```

---

## 🧪 API Testing

This API can be tested using:

* Postman
* EchoAPI (Visual Studio code Extention)
* Thunder Client (Visual Studio code Extention)

All protected endpoints require a valid JWT access token.

---
## 📌 Future Improvements

* Task search functionality
* Role-based permissions
* API documentation (Swagger)
* Dockerization
* Deployment (Render / Railway)

---

## 👤 Author

**Bayodele Faith**
Backend Developer

* Django REST Framework
* Node.js
* React
* Automation (n8n)

---

## ⭐️ Show Your Support

If you found this project useful, give it a ⭐️ to support the work!

