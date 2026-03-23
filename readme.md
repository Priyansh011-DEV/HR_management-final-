🚀 HR SaaS Management System (Full-Stack)

A multi-tenant, enterprise-grade HR management system built using Spring Boot + PostgreSQL, featuring secure authentication, role-based workflows, and a full-stack UI.

🧠 Overview

This project simulates a real-world HR SaaS (Software as a Service) platform where multiple companies can securely manage employees, roles, and leave workflows within a shared system.

It includes:

🔐 Secure authentication system (JWT)
🏢 Multi-tenant architecture (company isolation)
👨‍💼 Employee lifecycle management
📅 Leave management with approval workflows
🌐 Full-stack frontend (HTML + CSS + JS)
🏗️ Architecture

The application follows a clean layered architecture:

Controller Layer → Handles REST APIs
Service Layer → Business logic & validations
Repository Layer → Database interaction (JPA)
Entity Layer → Core models
DTO Layer → Secure data transfer
Security Layer → JWT + Spring Security
⚙️ Tech Stack
Backend: Java 17, Spring Boot
Security: Spring Security + JWT
Database: PostgreSQL
ORM: Spring Data JPA (Hibernate)
Build Tool: Maven
Utilities: Lombok
Frontend: HTML, CSS, JavaScript (Vanilla)
Deployment: Render (Backend), Docker (Configured)
🔐 Authentication & Security
JWT-based authentication (stateless)
Custom login API with token generation
Password encryption using BCrypt
Role-Based Access Control (ADMIN, HR, EMPLOYEE)
Secure endpoint access via JWT filter
Debugged real-world issues:
Token validation errors
Incorrect endpoint mapping
Spring Security filter chain handling
🏢 Multi-Tenant Architecture
Shared database with company-level isolation
Every user & employee linked to a company
Users can only access their company’s data
Designed for scalability (SaaS model)
👥 Company & User Management
Company registration with admin creation
User entity with roles and company mapping
One-to-One mapping:
User ↔ Employee
Fixed:
Infinite JSON recursion using @JsonIgnore
Entity ownership issues in JPA
👨‍💼 Employee Management Module
Create employee
View all employees (company-specific)
Update employee
Delete employee
Secure CRUD operations with role restrictions
📅 Leave Management System (Advanced Workflow)
🔥 Features
Employees can apply for leave
Leave status:
PENDING
APPROVED
REJECTED
🧠 Smart Approval Logic
HR can approve/reject Employee leaves
❌ HR cannot approve their own leave
ADMIN can approve:
Employee leaves
HR leaves

👉 This mimics real corporate hierarchy workflows

📡 API Endpoints
POST /api/leaves/apply → Apply for leave
GET /api/leaves/my → View own leaves
GET /api/leaves/all → (HR/Admin) View company leaves
PUT /api/leaves/{id}/approve → Approve leave
PUT /api/leaves/{id}/reject → Reject leave
🌐 Frontend (Full-Stack Integration)
✨ Features Implemented
Login Page (connected to backend JWT auth)
Registration Page
Dynamic Dashboards:
👨‍💼 Employee Dashboard
🧑‍💼 HR/Admin Dashboard
Employee Features:
Apply for leave
View leave history
HR/Admin Features:
View all leave requests
Approve / Reject leaves
Logout functionality
API integration using JavaScript (fetch)
🎨 UI/UX
Custom CSS dashboards
Role-based UI rendering
Clean and structured layout
Debugged real issues:
Button event binding failures
API response handling bugs
UI not updating after actions
🧩 Database Design
Core Entities
Company
User
Role
Employee
Leave
Relationships
Company → Users (One-to-Many)
Company → Employees (One-to-Many)
User → Employee (One-to-One)
Employee → Leave (One-to-Many)
🔒 Security Design
Stateless authentication (JWT)
Custom JWT filter
Role-based endpoint protection
Company-level data security
Password hashing (BCrypt)
🧪 Testing & Debugging
API testing using Postman
Real-world debugging experience:
JWT “Forbidden” errors
Wrong endpoint usage
Frontend-backend data mismatch
MongoDB-style reference issues (learned DB design tradeoffs)
🚀 Deployment
Backend deployed on Render
Dockerized application
Environment-based configuration
⚡ Future Enhancements
Leave balance tracking
Email notifications (SMTP integration)
Payroll management system
Attendance tracking system
Analytics dashboard (charts + insights)
React-based frontend upgrade
SaaS billing & subscription model
💡 Learning Outcomes
Built a production-style SaaS backend
Implemented JWT authentication from scratch
Designed multi-tenant architecture
Developed role-based real-world workflows
Integrated full-stack frontend with backend APIs
Solved real debugging challenges like a developer (not tutorial-level)
🏁 Status

✅ Full Backend Completed
✅ Frontend Integrated
🚧 Scaling & Enhancements Ongoing

📌 Author

Developed as a portfolio-grade full-stack SaaS project to demonstrate:

Backend Engineering
System Design
Security Implementation
Real-world Problem Solving


⚙️ How to Run Locally
🔧 Prerequisites

Make sure you have installed:

Java 17+
Maven
PostgreSQL
Git
📥 1. Clone the Repository
git clone https://github.com/your-username/hr-saas-system.git
cd hr-saas-system
🛠️ 2. Configure Database

Create a PostgreSQL database:

CREATE DATABASE hr_saas;
⚙️ 3. Update application.properties
spring.datasource.url=jdbc:postgresql://localhost:5432/hr_saas
spring.datasource.username=your_db_username
spring.datasource.password=your_db_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

jwt.secret=your_secret_key
▶️ 4. Run the Application

Using Maven:

mvn spring-boot:run

OR run from your IDE (IntelliJ / Eclipse)

🌐 5. Access the Application
Backend API:
http://localhost:8080
Frontend (if static HTML inside project):
Open in browser or via Spring Boot static resources
🔐 6. Test Authentication Flow
Register a company + admin
Login → get JWT token
Use token in headers:
Authorization: Bearer <your_token>
🧪 7. Test APIs

Use:

Postman
OR Frontend UI