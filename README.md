# School Management System

A **Java-based School Management System** built using **JDBC + MySQL** with a clean layered architecture (CLI → Service → DAO → Database).  
The system manages students, grades, classes, attendance, and academic marks, and is designed as a foundation for a full-scale school administration platform.

This project is intentionally built close to **real-world enterprise Java practices**, focusing on separation of concerns, data integrity, and maintainability.

---

## 📌 Features

### 🎓 Student Management
- Register new students
- View student details by ID
- List all students
- Update student information
- Activate / deactivate students

### 🏫 Academic Structure
- Grade management (Grade 8 – Grade 12)
- Class management per grade
- Student–grade relationships

### 🗓 Attendance Management
- Mark student attendance
- View attendance by student
- View attendance by date

### 📊 Marks & Assessments
- Add student marks per subject
- Weighted assessments (tests, exams, assignments)
- Calculate final subject averages

---

## 🧱 Project Architecture

```
SchoolManagementSystem/
│
├── src/
│   ├── ui/cli/              # Command-line interface
│   ├── student/
│   │   ├── model/
│   │   ├── dao/
│   │   └── service/
│   ├── attendance/
│   │   ├── model/
│   │   ├── dao/
│   │   └── service/
│   ├── classmgmt/
│   │   ├── model/
│   │   ├── dao/
│   │   └── service/
│   ├── marks/
│   │   ├── model/
│   │   ├── dao/
│   │   └── service/
│   ├── core/db/             # Database connection utilities
│   └── Main.java
│
├── lib/                     # MySQL JDBC Driver
├── out/                     # Compiled classes
├── sql/                     # Database schema & seed scripts
└── README.md
```

---

## 🗄 Database Design

- **students**
- **grades**
- **classes**
- **subjects**
- **student_subjects**
- **attendance**
- **assessments**
- **student_marks**

Relational integrity is enforced via:
- Foreign keys
- Composite primary keys
- Enum constraints (e.g. Gender)

---

## ⚙️ Technologies Used

- **Java (JDK 21+)**
- **MySQL 8+**
- **JDBC (mysql-connector-j)**
- **CLI-based UI**
- **Git & GitHub**

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Labious-pheto/SchoolManagementSystem.git
cd SchoolManagementSystem
```

---

### 2️⃣ Database Setup

Create the database:

```sql
CREATE DATABASE school_management;
USE school_management;
```

Run the SQL scripts located in the `sql/` folder to create tables and seed data.

---

### 3️⃣ Configure Database Connection

Edit the file:

```
src/core/db/DBConnection.java
```

Update credentials:

```java
private static final String URL = "jdbc:mysql://localhost:3306/school_management";
private static final String USER = "root";
private static final String PASSWORD = "your_password";
```

---

### 4️⃣ Compile the Project

From the project root:

```powershell
javac -cp ".;lib/mysql-connector-j-9.6.0.jar" -d out (Get-ChildItem -Recurse -Filter *.java | ForEach-Object { $_.FullName })
```

---

### 5️⃣ Run the Application

```powershell
java -cp ".;lib/mysql-connector-j-9.6.0.jar;out" Main
```

---

## 🖥 Sample CLI Menu

```
===== STUDENT MANAGEMENT =====
1. Register Student
2. View Student by ID
3. List All Students
4. Update Student
5. Deactivate Student
6. Mark Attendance
7. View Attendance by Student
8. View Attendance by Date
9. Add Class
10. List Classes
11. Add Student Mark
12. View Final Marks
0. Exit
```

---

## 📈 Learning Objectives

This project demonstrates:
- JDBC CRUD operations
- Layered architecture (DAO / Service / UI)
- SQL relational modelling
- Exception handling
- Input validation
- Realistic backend workflows

---

## 🔮 Future Improvements

- Role-based authentication (Admin / Teacher)
- REST API (Spring Boot)
- Web or JavaFX UI
- Reporting (PDF / CSV)
- Pagination & search

---

## 👤 Author

**Labious Phetoane**  
Junior Java Developer | SQL | Backend Systems
+2762 858 5758
estphetoane@gmail.com
---

## 📄 License

This project is open-source and intended for educational and portfolio purposes.

