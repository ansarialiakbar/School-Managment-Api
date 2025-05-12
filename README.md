# 🏫 School Management API

A RESTful API built with **Node.js**, **Express.js**, and **MySQL** to manage school data. The system allows users to **add new schools** and **retrieve a list of schools sorted by proximity** to a given location.

---

## 🚀 Features

- Add a new school with name, address, latitude, and longitude
- Retrieve all schools sorted by distance from a given latitude/longitude
- Input validation for secure and clean data
- MySQL database integration
- Organized project structure with routes and controllers
- Health check endpoint (`/`)

---

## 🛠️ Technologies Used

- Node.js
- Express.js
- MySQL
- Dotenv
- Nodemon (for development)

---

## 📁 Project Structure

school-management-api/
│
├── controllers/
│ └── schoolController.js # Logic for API endpoints
│
├── routes/
│ └── schoolRoutes.js # All routes defined here
│
├── db.js # MySQL connection setup
├── .env # Environment variables (DB config)
├── index.js # Entry point of the app
├── school_db.sql # SQL script to create DB and table
└── README.md # Project documentation


---

## 🧪 API Endpoints

### ➕ Add School

- **URL:** `/addSchool`
- **Method:** `POST`
- **Payload (JSON):**

```json
{
  "name": "School Name",

  "address": "123 Street, City",

  "latitude": -33.865143,

  "longitude": 151.209900
}
```

**. Response:**



```json
{
  "message": "School added successfully"
}
```

## 📍 List Schools by Proximity

**. URL:** /listSchools?latitude=<your_lat>&longitude=<your_long>

**. Method:** GET

**. Example:**


```
/listSchools?latitude=-33.870&longitude=151.200
```
**. Response:**

```json

[
  {
    "id": 2,
    "name": "Green Valley Public School",
    "address": "12 Hill Street, Sydney NSW",
    "latitude": -33.865143,
    "longitude": 151.2099,
    "distance": 0.59
  },
  ...
]
```

## ✅ Health Check

**. URL:** /

**. Method:** GET

**. Response:** Server is running fine!

## 🧾 Setup Instructions

**1️⃣ Clone the Repository**
```
git clone https://github.com/ansarialiakbar/School-Managment-Api.git
cd school-management-api
```

**2️⃣ Install Dependencies**
```
npm install
```

**3️⃣ Configure Environment Variables**

Create a .env file in the root directory:

```dotenv

DB_HOST=localhost

DB_USER=root

DB_PASSWORD=yourpassword

DB_NAME=school_db

PORT=3000
```

**4️⃣ Set Up MySQL Database**

Run the provided SQL script:
```
mysql -u root -p < school_db.sql
```

**5️⃣ Start the Server**
```
npm start
```
Server will run at: http://localhost:3000

## 👨‍💻 Author

Developed by **Ali Akbar Ansari**

## 📃 License

This project is licensed under the MIT License.