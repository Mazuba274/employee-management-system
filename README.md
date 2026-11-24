# Employee Management System (EMS)

A full-stack Employee Management System built with **Java Spring Boot**, **React**, **Vite**, and **MySQL**. The application provides a RESTful API and a web-based interface for managing employee records.

## Project Overview

The Employee Management System is designed to simplify employee record management through a web application connected to a relational database.

The backend exposes REST APIs for employee operations, while the React frontend provides an interface for interacting with those APIs.

## Technology Stack

| Component | Technology |
|---|---|
| Backend | Java 17, Spring Boot 3.5.6 |
| Backend build tool | Maven |
| Frontend | React 19 |
| Frontend tooling | Vite 7 |
| Database | MySQL 8 |
| API communication | REST API |
| HTTP client | Axios |
| UI framework | Bootstrap 5 |
| Routing | React Router |
| API testing | Postman |
| Version control | Git and GitHub |

## Features

- **Employee Management:** Create, view, update and delete employee records.
- **Employee Listing:** Display available employee records.
- **Employee Registration:** Add employees using their personal and contact details.
- **Employee Editing:** Update existing employee information.
- **RESTful API:** Backend endpoints for employee data operations.
- **Database Integration:** Persistent storage using MySQL.
- **Frontend and Backend Integration:** React communicates with Spring Boot through Axios.

## System Architecture

```text
       USER
         |
         v
  REACT FRONTEND
    (Vite)
         |
         | HTTP / Axios
         v
  SPRING BOOT BACKEND
         |
         v
    REST CONTROLLER
         |
         v
    SERVICE LAYER
         |
         v
   REPOSITORY LAYER
         |
         v
       MYSQL
```

## Project Structure

```text
original-EMS/
│
├── ems-backend/
│   └── ems-backend/
│       ├── src/
│       │   ├── main/
│       │   │   ├── java/net/mazuba/ems/
│       │   │   │   ├── controller/
│       │   │   │   ├── dto/
│       │   │   │   ├── entity/
│       │   │   │   ├── exception/
│       │   │   │   ├── mapper/
│       │   │   │   ├── repository/
│       │   │   │   └── service/
│       │   │   └── resources/
│       │   │       └── application.properties
│       │   └── test/
│       ├── pom.xml
│       └── mvnw.cmd
│
├── ems-frontend/
│   └── ems-frontend/
│       ├── public/
│       ├── src/
│       │   ├── components/
│       │   ├── services/
│       │   ├── App.jsx
│       │   ├── App.css
│       │   └── main.jsx
│       ├── package.json
│       └── vite.config.js
│
├── .gitignore
└── README.md
```

## Prerequisites

Install the following before running the application:

- Java Development Kit (JDK) 17 or later
- Node.js compatible with Vite 7 (Node.js 20.19+ or 22.12+)
- MySQL Server 8.0 or later
- Git
- Visual Studio Code or another IDE
- Postman (optional, for API testing)

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Mazuba274/employee-management-system.git
cd employee-management-system
```

### 2. Configure the MySQL database

Open MySQL and execute:

```sql
CREATE DATABASE ems;
```

The application uses environment variables for database credentials.

### 3. Configure backend environment variables

In Windows PowerShell, set:

```powershell
$env:DB_URL="jdbc:mysql://localhost:3306/ems"
$env:DB_USERNAME="root"
$env:DB_PASSWORD="YOUR_MYSQL_PASSWORD"
```

Replace the password placeholder with your own local MySQL password. Never commit actual credentials to GitHub.

### 4. Run the Spring Boot backend

Open a terminal in:

```text
ems-backend/ems-backend
```

Execute:

```powershell
.\mvnw.cmd spring-boot:run
```

The backend runs at:

```text
http://localhost:8080
```

### 5. Run the React frontend

Open another terminal in:

```text
ems-frontend/ems-frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Open the frontend using the local URL displayed by Vite, normally:

```text
http://localhost:5173
```

## REST API Documentation

Base URL:

```text
http://localhost:8080/api/employees
```

| HTTP Method | Endpoint | Description |
|---|---|---|
| POST | `/api/employees` | Create an employee |
| GET | `/api/employees` | Retrieve all employees |
| GET | `/api/employees/{id}` | Retrieve an employee by ID |
| PUT | `/api/employees/{id}` | Update an employee |
| DELETE | `/api/employees/{id}` | Delete an employee |

### Example employee request

**POST** `/api/employees`

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com"
}
```

The employee entity contains:

- `id`
- `firstName`
- `lastName`
- `email`

## Testing

The REST API can be tested using Postman.

Test the following operations:

1. Create a new employee.
2. Retrieve all employees.
3. Retrieve an employee using their ID.
4. Update an employee.
5. Delete an employee.

Verify that the changes are reflected in the MySQL database.

## Configuration and Security

- Database credentials are supplied through environment variables.
- Do not commit `.env` files, database passwords, API tokens or other secrets.
- Use a dedicated database account with appropriate permissions rather than exposing production database credentials.
- Configure CORS restrictions and additional security controls before deploying the application publicly.

## Current Project Status

The repository contains the initial full-stack implementation of employee CRUD functionality.

Further improvements can include authentication and role-based access control, automated testing, enhanced validation, deployment and additional HR management features.

## Author

**Mazuba Hamuchenje**

Computer Science Graduate | Software Development | IT

GitHub: [Mazuba274](https://github.com/Mazuba274)

## Repository

[Employee Management System on GitHub](https://github.com/Mazuba274/employee-management-system)
