# Team Sync

**Team Sync** is a role-based employee management and team administration web application built with React.

The application provides separate experiences for **Administrators** and **Employees**, with authentication, protected routes, role-based authorization, employee management, task management, department management, document management, attendance, and profile management.

## ✨ Features

### 🔐 Authentication

* User registration
* User login
* Authentication state management
* Protected application routes
* Public and private route handling
* Automatic authentication state verification

### 👨‍💼 Admin Module

Administrators have access to management features such as:

* View employees
* Add employees
* Employee statistics
* Search and filter employees
* Employee pagination
* Task management
* Department management
* Document management

### 👨‍💻 Employee Module

Employees have access to their own workspace, including:

* My Tasks
* Attendance
* Profile management

### 🛡️ Role-Based Authorization

The application uses role-based routing to control access to different sections of the dashboard.

There are dedicated route configurations for:

* Common routes
* Admin routes
* Employee routes

This prevents users from accessing pages that are not intended for their role.

## 🛠️ Tech Stack

### Frontend

* **React**
* **Vite**
* **React Router**
* **Tailwind CSS**

### State Management

* **Redux Toolkit**
* **React Redux**
* **TanStack React Query**

### API & Forms

* **Axios**
* **React Hook Form**

### UI

* **Lucide React**

## 📁 Project Structure

```text
src/
│
├── app/
│   ├── constants/
│   │   └── navigations.jsx
│   │
│   ├── layouts/
│   │   ├── AuthLayout.jsx
│   │   └── DashboardLayout.jsx
│   │
│   ├── protectedRoutes/
│   │   ├── ProtectedRoute.jsx
│   │   ├── PublicRoute.jsx
│   │   └── RoleBaseRoute.jsx
│   │
│   ├── routes/
│   │   ├── AppRoutes.jsx
│   │   ├── adminRoutes.jsx
│   │   ├── commonRoutes.jsx
│   │   └── employeeRoutes.jsx
│   │
│   └── store.jsx
│
├── config/
│   └── axiosInstance.jsx
│
├── features/
│   │
│   ├── auth/
│   │   └── ...
│   │
│   ├── dashboard/
│   │   └── ...
│   │
│   ├── admin module/
│   │   ├── departments/
│   │   ├── documents/
│   │   ├── employees/
│   │   └── tasks/
│   │
│   └── employee module/
│       ├── Attendance/
│       ├── MyTask/
│       └── profile/
│
├── assets/
│
├── App.jsx
├── main.jsx
└── index.css
```

## 🧭 Application Routes

### Public Routes

```text
/
├── Login
└── /register
```

### Admin Routes

```text
/home/employee
/home/add-employee
/home/task
/home/department
/home/document
```

### Employee Routes

```text
/home/myTask
/home/attendance
/home/profile
```

Authenticated users enter the dashboard through the `/home` route, while role-based route guards determine which admin or employee pages they can access.

## 👥 Employee Management

The employee management section provides an administrative interface for working with employees.

It includes:

* Employee listing
* Employee statistics
* Search and filtering
* Pagination
* Employee-related actions
* Add employee functionality

The employee interface is divided into reusable components such as:

```text
EmployeeHeader
EmployeeStats
SearchFilterBar
EmployeeTable
Pagination
```

This keeps the page structure modular and easier to maintain.

## 🔄 Data Management

The application uses different tools for different types of state:

* **Redux Toolkit** for global application state
* **TanStack React Query** for server-side data and asynchronous requests
* **Axios** for HTTP communication
* **React Hook Form** for form handling and validation

This separation helps keep UI state, application state, and server data organized.

## 🔒 Protected Routes

Team Sync uses multiple route guards:

### PublicRoute

Controls access to authentication-related pages.

### ProtectedRoute

Ensures that only authenticated users can access the main application.

### RoleBaseRoute

Checks the user's role before allowing access to role-specific pages.

The routing architecture is organized so that authentication and authorization are handled before rendering protected dashboard features.

## 🎨 UI & Styling

The application uses **Tailwind CSS** for styling and utility-based responsive layouts.

Reusable components are used throughout the dashboard to keep the UI consistent and maintainable.

**Lucide React** is used for interface icons.

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Devendradhote001/final_project_Frontend.git
```

### 2. Navigate to the project

```bash
cd final_project_Frontend
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the development server

```bash
npm run dev
```

The application will start using the Vite development server.

## 📜 Available Scripts

### Development

```bash
npm run dev
```

Starts the development server.

### Production Build

```bash
npm run build
```

Creates an optimized production build.

### Lint

```bash
npm run lint
```

Runs ESLint to check the codebase.

### Preview

```bash
npm run preview
```

Runs a local preview of the production build.

## 🏗️ Architecture

The project follows a **feature-based frontend architecture**.

Instead of putting every component, page, and logic file into a single large folder, functionality is divided into independent modules.

For example:

```text
features/
├── auth/
├── dashboard/
├── admin module/
└── employee module/
```

Application-level concerns such as routing, layouts, protected routes, and global state are kept separately inside `app/`.

This structure makes the project easier to:

* Maintain
* Scale
* Debug
* Add new features
* Reuse components
* Manage role-specific functionality

## 🚀 Future Improvements

Possible improvements for future versions include:

* Comprehensive automated testing
* Improved loading and error states
* More granular role permissions
* Enhanced accessibility
* Improved mobile responsiveness
* Better form validation and feedback
* Advanced employee analytics
* Notification system
* Improved dashboard customization

## 📄 License

This project is developed for educational and project purposes.

---

**Team Sync** — Employee Management & Team Administration Platform
