Here is a detailed README documentation for your project, explaining the structure, features, usage, and expected output.
# Employee Management System (EMS)

A simple Employee Management System built with **React** and **Vite**, styled using **Tailwind CSS**. This project allows an admin to assign tasks to employees, and employees to view and manage their tasks.
For storing Data use : Localstorage and for Global State Management use : Context Api

---

**Deployment Link:** 
https://ems-main-ruby.vercel.app/

---

## Table of Contents

- [Project Structure](#project-structure)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Component Overview](#component-overview)
- [Sample Output](#sample-output)
- [Scripts](#scripts)
- [Customization](#customization)

---

## Project Structure
ems-main/ ├── public/ │ └── vite.svg ├── src/ │ ├── App.jsx │ ├── main.jsx │ ├── index.css │ ├── App.css │ ├── assets/ │ ├── components/ │ │ ├── Auth/ │ │ │ └── Login.jsx │ │ ├── Dashboard/ │ │ │ ├── AdminDashboard.jsx │ │ │ └── EmployeeDashboard.jsx │ │ ├── TaskList/ │ │ │ ├── AcceptTask.jsx │ │ │ ├── CompleteTask.jsx │ │ │ ├── FailedTask.jsx │ │ │ ├── NewTask.jsx │ │ │ └── TaskList.jsx │ │ └── other/ │ │ ├── AllTask.jsx │ │ ├── CreateTask.jsx │ │ ├── Header.jsx │ │ └── TaskListNumbers.jsx │ ├── context/ │ │ └── AuthProvider.jsx │ └── utils/ │ └── localStorage.jsx ├── index.html ├── package.json ├── tailwind.config.js ├── postcss.config.js └── vite.config.js

---

## Features

- **Admin Login:** Admin can log in and assign tasks to employees.
- **Employee Login:** Employees can log in to view and manage their tasks.
- **Task Assignment:** Admin can create and assign tasks to employees.
- **Task Status:** Tasks can be marked as New, Accepted, Completed, or Failed.
- **Dashboard:** Separate dashboards for Admin and Employees.
- **Persistent Data:** Uses browser localStorage for data persistence.

---

## Getting Started

### Prerequisites

- Node.js (v16+ recommended)
- npm

### Installation

1. **Clone the repository:**
   ```sh
   git clone <your-repo-url>
   cd ems-main

2. **Or download project respository:**
   ```sh
   Click on code
   then click on download zip
   
3. **Install dependencies:**
   npm install
   
4. **Run the development server:**
   npm run dev
   
5. **Open http://localhost:5173 in your browser**.
---
**Usage**
**-Login**
Admin:
Email: admin@example.com
Password: 123

Employee:
Use one of the emails from src/utils/localStorage.jsx (e.g., e@e.com, employee2@example.com, etc.)
Password: 123

Admin Dashboard
Assign tasks to employees using the "Create Task" form.
View all employees and their task counts.
Employee Dashboard
View your assigned tasks.
Mark tasks as completed or failed (UI only, logic can be extended).

---
**Component Overview**
App.jsx: Main app logic, handles routing between dashboards and login.
AuthProvider.jsx: Provides user data context.
Login.jsx: Login form for both admin and employees.
AdminDashboard.jsx: Admin's dashboard.
EmployeeDashboard.jsx: Employee's dashboard.
CreateTask.jsx: Form for admin to create tasks.
AllTask.jsx: Shows all employees and their task stats.
TaskList.jsx: Renders tasks for an employee.
AcceptTask.jsx, NewTask.jsx, CompleteTask.jsx, FailedTask.jsx: Task cards for different statuses.
TaskListNumbers.jsx: Shows task counts for an employee.
Header.jsx: Displays greeting and logout button.
localStorage.jsx: Handles initial data and localStorage logic.

---
**Sample Output**
Login Screen
+--------------------------------------+
|   [ Enter your email ]               |
|   [ Enter password ]                 |
|   [ Log in ]                         |
+--------------------------------------+

--- 
**Dashboard**

**Admin Dashboard**
Header: "Hello" and "Log Out" button.
Create Task: Form to assign tasks.
All Employees: Table showing each employee's task counts.

**Employee Dashboard**
Header: "Hello" and "Log Out" button.
Task Stats: Cards showing New, Completed, Accepted, and Failed task counts.
Task List: Scrollable list of task cards (New, Accepted, Completed, Failed).

---
**Scripts**
npm run dev - Start the development server.
npm run build - Build for production.
npm run preview - Preview the production build.
npm run lint - Run ESLint.

---
**Customization**
Add Employees: Edit the employees array in localStorage.jsx.
Change Task Logic: Update task status logic in the respective TaskList components.
Styling: Modify Tailwind classes in component files or update tailwind.config.js.

---
**Response and Output**
On successful login: Redirects to the appropriate dashboard.
On task creation: Task is added to the selected employee and displayed in their dashboard.
On logout: Returns to the login screen.

---
## Sample Data (localStorage)

The application initializes with the following data in localStorage:

### Employees

```json
[
  {
    "id": 1,
    "firstName": "Arjun",
    "email": "e@e.com",
    "password": "123",
    "taskCounts": {
      "active": 2,
      "newTask": 1,
      "completed": 1,
      "failed": 0
    },
    "tasks": [
      {
        "active": true,
        "newTask": true,
        "completed": false,
        "failed": false,
        "taskTitle": "Update website",
        "taskDescription": "Revamp the homepage design",
        "taskDate": "2024-10-12",
        "category": "Design"
      },
      {
        "active": false,
        "newTask": false,
        "completed": true,
        "failed": false,
        "taskTitle": "Client meeting",
        "taskDescription": "Discuss project requirements",
        "taskDate": "2024-10-10",
        "category": "Meeting"
      },
      {
        "active": true,
        "newTask": false,
        "completed": false,
        "failed": false,
        "taskTitle": "Fix bugs",
        "taskDescription": "Resolve bugs reported in issue tracker",
        "taskDate": "2024-10-14",
        "category": "Development"
      }
    ]
  },
  {
    "id": 2,
    "firstName": "Sneha",
    "email": "employee2@example.com",
    "password": "123",
    "taskCounts": {
      "active": 1,
      "newTask": 0,
      "completed": 1,
      "failed": 0
    },
    "tasks": [
      {
        "active": true,
        "newTask": false,
        "completed": false,
        "failed": false,
        "taskTitle": "Database optimization",
        "taskDescription": "Optimize queries for better performance",
        "taskDate": "2024-10-11",
        "category": "Database"
      },
      {
        "active": false,
        "newTask": false,
        "completed": true,
        "failed": false,
        "taskTitle": "Design new feature",
        "taskDescription": "Create mockups for the new feature",
        "taskDate": "2024-10-09",
        "category": "Design"
      }
    ]
  },
  {
    "id": 3,
    "firstName": "Ravi",
    "email": "employee3@example.com",
    "password": "123",
    "taskCounts": {
      "active": 2,
      "newTask": 1,
      "completed": 1,
      "failed": 0
    },
    "tasks": [
      {
        "active": true,
        "newTask": true,
        "completed": false,
        "failed": false,
        "taskTitle": "Prepare presentation",
        "taskDescription": "Prepare slides for upcoming client presentation",
        "taskDate": "2024-10-13",
        "category": "Presentation"
      },
      {
        "active": true,
        "newTask": false,
        "completed": false,
        "failed": false,
        "taskTitle": "Code review",
        "taskDescription": "Review the codebase for optimization",
        "taskDate": "2024-10-12",
        "category": "Development"
      },
      {
        "active": false,
        "newTask": false,
        "completed": true,
        "failed": false,
        "taskTitle": "Testing",
        "taskDescription": "Test the latest build for bugs",
        "taskDate": "2024-10-08",
        "category": "QA"
      }
    ]
  },
  {
    "id": 4,
    "firstName": "Priya",
    "email": "employee4@example.com",
    "password": "123",
    "taskCounts": {
      "active": 2,
      "newTask": 1,
      "completed": 0,
      "failed": 0
    },
    "tasks": [
      {
        "active": true,
        "newTask": true,
        "completed": false,
        "failed": false,
        "taskTitle": "Write documentation",
        "taskDescription": "Update the project documentation",
        "taskDate": "2024-10-13",
        "category": "Documentation"
      },
      {
        "active": true,
        "newTask": false,
        "completed": false,
        "failed": false,
        "taskTitle": "Set up CI/CD",
        "taskDescription": "Implement continuous integration pipeline",
        "taskDate": "2024-10-11",
        "category": "DevOps"
      }
    ]
  },
  {
    "id": 5,
    "firstName": "Karan",
    "email": "employee5@example.com",
    "password": "123",
    "taskCounts": {
      "active": 2,
      "newTask": 1,
      "completed": 1,
      "failed": 0
    },
    "tasks": [
      {
        "active": true,
        "newTask": true,
        "completed": false,
        "failed": false,
        "taskTitle": "UI redesign",
        "taskDescription": "Redesign the user interface for better UX",
        "taskDate": "2024-10-14",
        "category": "Design"
      },
      {
        "active": false,
        "newTask": false,
        "completed": true,
        "failed": false,
        "taskTitle": "Deploy new build",
        "taskDescription": "Deploy the latest build to production",
        "taskDate": "2024-10-09",
        "category": "DevOps"
      },
      {
        "active": true,
        "newTask": false,
        "completed": false,
        "failed": false,
        "taskTitle": "Client feedback",
        "taskDescription": "Gather feedback from clients after product launch",
        "taskDate": "2024-10-12",
        "category": "Support"
      }
    ]
  }
]

**Admin**
[
  {
    "id": 1,
    "email": "admin@example.com",
    "password": "123"
  }
]
