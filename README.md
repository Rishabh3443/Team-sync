# Team Sync

A role-based employee management and team collaboration frontend built with **React** and **Vite**.

Team Sync provides separate workflows for **administrators** and **employees**, with protected routing, authentication, employee management, task management, attendance, departments, documents, and profile management.

## 🚀 Features

### Authentication

* User registration and login
* Authentication-aware routing
* Persistent logged-in employee state
* Automatic access-token refresh on `401` responses
* Redirect to login when authentication fails

### Role-Based Access

The application separates access based on user roles:

**Admin**

* Employee management
* Add employees
* Task management
* Department management
* Document management

**Employee**

* View and manage assigned tasks
* Attendance
* Profile management

Common dashboard routes are also available to authenticated users.

## 🛠️ Tech Stack

### Frontend

* React
* React Router
* Vite
* Tailwind CSS

### State Management

* Redux Toolkit
* React Redux
* TanStack React Query

### Forms & API

* React Hook Form
* Axios
* Axios Interceptors

### UI

* Lucide React

The project dependencies are defined in `package.json`.

## 📂 Project Structure

```text
src/
├── app/
│   ├── constants/
│   │   └── navigations.jsx
│   ├── layouts/
│   │   ├── AuthLayout.jsx
│   │   └── DashboardLayout.jsx
│   ├── protectedRoutes/
│   │   ├── ProtectedRoute.jsx
│   │   ├── PublicRoute.jsx
│   │   └── RoleBaseRoute.jsx
│   ├── routes/
│   │   ├── AppRoutes.jsx
│   │   ├── adminRoutes.jsx
│   │   ├── commonRoutes.jsx
│   │   └── employeeRoutes.jsx
│   └── store.jsx
│
├── config/
│   └── axiosInstance.jsx
│
├── features/
│   ├── auth/
│   ├── dashboard/
│   ├── admin module/
│   │   ├── departments/
│   │   ├── documents/
│   │   ├── employees/
│   │   └── tasks/
│   └── employee module/
│       ├── Attendance/
│       ├── MyTask/
│       └── profile/
│
├── App.jsx
├── main.jsx
└── index.css
```

The project follows a feature-oriented structure, separating application-level routing/layout logic from individual business modules.

## 🔐 Routing & Authorization

Team Sync uses React Router with dedicated route guards:

* `PublicRoute` protects authentication pages from already authenticated users.
* `ProtectedRoute` ensures authenticated users can access the dashboard.
* `RoleBaseRoute` restricts routes based on the user's role.

The main application routes are organized under `/` for authentication and `/home` for authenticated dashboard functionality.

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

These route groups are explicitly separated in the application routing configuration.

## 🌐 API Integration

The frontend communicates with the Team Sync backend through a centralized Axios instance.

```js
baseURL: "https://api.team-sync.space/api"
```

The Axios configuration uses credentials and includes response interception for authentication failures. When a request receives a `401`, the application attempts to obtain a new access token and retries the original request.

## 👥 Employee Management

The admin employee module includes:

* Employee statistics
* Employee listing
* Search and filtering
* Pagination
* Employee-related actions
* Employee creation

The employee page is composed from dedicated UI components such as `EmployeeHeader`, `EmployeeStats`, `SearchFilterBar`, `EmployeeTable`, and `Pagination`.

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Devendradhote001/final_project_Frontend.git
```

### 2. Navigate into the project

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

The project uses Vite for local development and provides the standard `dev`, `build`, `lint`, and `preview` scripts.

## 📦 Available Scripts

```bash
npm run dev
```

Starts the Vite development server.

```bash
npm run build
```

Creates a production build.

```bash
npm run lint
```

Runs ESLint across the project.

```bash
npm run preview
```

Previews the production build locally.

## 🏗️ Architecture

The application is organized around a few core architectural ideas:

**Feature-based organization**
Business functionality is grouped into independent feature modules.

**Centralized state management**
Redux Toolkit and React Redux are used for application state, while TanStack React Query handles server-state and data-fetching concerns.

**Protected and role-based routing**
Authentication and authorization are enforced at the routing level instead of relying only on individual pages.

**Reusable API layer**
Axios configuration is centralized so API calls and authentication-refresh behavior can be handled consistently.

## 🔮 Future Improvements

Potential improvements include:

* Better loading and error states
* More robust form validation
* Enhanced responsive design
* Automated testing
* Improved accessibility
* Better empty-state handling
* More granular permissions
* Production monitoring and error tracking

## 📄 License

This project is intended for learning and project-development purposes.

---

Built with **React + Vite**.
