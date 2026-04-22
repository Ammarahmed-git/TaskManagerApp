<div align="center">

# ✅ TaskManager

### *Stop forgetting. Start delivering.*

[![C#](https://img.shields.io/badge/Language-C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![ASP.NET MVC](https://img.shields.io/badge/Framework-ASP.NET%20MVC-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/en-us/apps/aspnet/mvc)
[![Visual Studio](https://img.shields.io/badge/IDE-Visual%20Studio-5C2D91?style=for-the-badge&logo=visualstudio&logoColor=white)](https://visualstudio.microsoft.com/)
[![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://www.microsoft.com/en-us/sql-server)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

<br/>

> 🛠️ A full-stack ASP.NET MVC web app with user auth, role-based access control, and complete task lifecycle management.

<br/>

---

</div>

## 📖 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Database Schema](#-database-schema)
- [User Roles](#-user-roles)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [User Stories](#-user-stories)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🧩 About

**TaskManager** is a web-based Task Management System built with **ASP.NET MVC** and **C#**. It provides a clean, role-aware interface for teams or individuals to create, track, and manage tasks through their full lifecycle — from *To Do* all the way to *Done*.

Authentication and role-based authorization ensure that your data stays organized and access-controlled, whether you're a regular team member or an admin keeping things in order.

---

## ✨ Features

### 🔐 User Authentication & Registration
- Secure **user registration** with username & password
- Full **login / logout** session management
- Password-protected routes — no sneaking in without credentials

### 📋 Task Management (CRUD)
- Create tasks with a **title**, **description**, **due date**, and **status**
- View all tasks in a clean, sortable **list view**
- **Edit** task details at any time
- **Delete** tasks (admin-only for safety)

### 🔄 Task Status Workflow
Track every task through its lifecycle:

```
[ To Do ] ──► [ In Progress ] ──► [ Done ]
```

- Status can be updated at any time by the task owner
- Visual indicators make it easy to see what needs attention

### 👥 Role-Based Access Control
| Action | Regular User | Administrator |
|---|:---:|:---:|
| Register / Login | ✅ | ✅ |
| Create Tasks | ✅ | ✅ |
| Edit Own Tasks | ✅ | ✅ |
| View All Tasks | ✅ | ✅ |
| Delete Tasks | ❌ | ✅ |
| Manage Users | ❌ | ✅ |

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| **Language** | C# |
| **Framework** | ASP.NET MVC |
| **IDE** | Visual Studio |
| **Database** | Microsoft SQL Server |
| **ORM** | Entity Framework |
| **Auth** | ASP.NET Identity |
| **Frontend** | Razor Views, HTML5, CSS3, Bootstrap |
| **Config** | Web.config (Debug / Release profiles) |

---

## 🗄 Database Schema

```
┌──────────────┐          ┌──────────────────────┐
│    Users     │          │        Tasks         │
├──────────────┤          ├──────────────────────┤
│ Id (PK)      │──────────│ Id (PK)              │
│ Username     │  1 : N   │ Title                │
│ PasswordHash │          │ Description          │
│ Role         │          │ DueDate              │
└──────────────┘          │ Status               │
                          │ UserId (FK)          │
                          └──────────────────────┘
```

**Task Status Enum:** `ToDo` | `InProgress` | `Done`  
**User Roles:** `User` | `Administrator`

---

## 👥 User Roles

### 👤 Regular User
A registered user can manage their own tasks — create, view, and update status — but cannot delete tasks or access admin panels.

### 🛡️ Administrator
An admin has full control: they can delete any task, manage user accounts, and oversee the entire task board across all users.

---

## 🚀 Getting Started

### Prerequisites

- **Visual Studio 2019+** (with ASP.NET workload)
- **.NET Framework 4.x** or **.NET 6+** (check `.csproj` for target)
- **SQL Server** (LocalDB works fine for development)
- **NuGet** package manager

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Ammarahmed-git/TaskManagerApp.git

# 2. Open the solution in Visual Studio
#    File → Open → Project/Solution → TaskManagementSystem.sln
```

```bash
# 3. Restore NuGet packages
#    Right-click Solution → Restore NuGet Packages
#    Or via Package Manager Console:
Update-Package -reinstall
```

```bash
# 4. Set up the database
#    In Package Manager Console:
Enable-Migrations
Update-Database
```

```bash
# 5. Run the application
#    Press F5 or click the green ▶ Run button in Visual Studio
#    App will open at https://localhost:{port}
```

> 💡 **Tip:** Update the connection string in `Web.config` to point to your local SQL Server instance if the default LocalDB doesn't work.

---

## 📁 Project Structure

```
TaskManagerApp/
├── Controllers/              # MVC Controllers (Tasks, Account, Admin)
├── Models/                   # Entity models & ViewModels
├── Views/                    # Razor .cshtml templates
│   ├── Tasks/                # Task list, create, edit, detail views
│   ├── Account/              # Login & Register views
│   └── Shared/               # Layout, nav, error pages
├── App_Data/                 # Local DB files (if using LocalDB)
├── Global.asax               # App entry point & route config
├── Global.asax.cs            # Application event handlers
├── Web.config                # App configuration & connection strings
├── Web.Debug.config          # Debug-specific config transforms
├── Web.Release.config        # Release-specific config transforms
├── packages.config           # NuGet dependencies
└── TaskManagementSystem.sln  # Visual Studio solution file
```

---

## 📝 User Stories

| Role | Story |
|---|---|
| Guest | I can register a new account to get started |
| Guest | I can log in with my credentials to access my tasks |
| User | I can create a task with a title, description, and due date |
| User | I can view all my tasks in a single dashboard |
| User | I can update the status of my task as I make progress |
| User | I can edit a task's details if requirements change |
| Admin | I can delete any task from the system |
| Admin | I can manage all users and their roles |

---

## 📱 Screenshots

> _Coming soon — screenshots will be added here._

<!-- Uncomment and replace paths once you have screenshots:
| Login | Task List | Create Task | Admin Panel |
|-------|-----------|-------------|-------------|
| ![Login](screenshots/login.png) | ![Tasks](screenshots/tasklist.png) | ![Create](screenshots/create.png) | ![Admin](screenshots/admin.png) |
-->

---

## 🤝 Contributing

All contributions are welcome! Here's how to get involved:

1. **Fork** the repository
2. **Create** your feature branch — `git checkout -b feature/your-feature`
3. **Commit** your changes — `git commit -m 'Add your feature'`
4. **Push** to the branch — `git push origin feature/your-feature`
5. **Open** a Pull Request

Please test thoroughly before submitting and keep code style consistent with the rest of the project.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ by [Ammar Ahmed](https://github.com/Ammarahmed-git)

🎯 *A practice project — built to learn, shared to inspire.*

⭐ Found it helpful? Drop a star!

</div>
