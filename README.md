# Employee Management System ✅

**A lightweight Java Swing application for basic employee CRUD (Create, Read, Update, Delete) operations with MySQL.**

---

## 🚀 Summary

This project provides a clean, dark-styled desktop UI to manage employee records: add, view, update, and remove employees, plus a simple login screen. It's built with Java (Swing) and uses a MySQL database for persistence.

## 🔧 Features

- Add new employee records (ID auto-generated in UI)
- View and search records (print support)
- Update employee details
- Remove employee entries
- Simple login screen (credentials stored in `login` table)
- Polished dark-themed Swing UI components

## 🧩 Tech stack

- Java 8 (source/target set to 1.8)
- Swing UI
- MySQL (database)
- JCalendar (`com.toedter: jcalendar`) used for date picker
- rs2xml (`net.proteanit:rs2xml`) for ResultSet -> TableModel conversion
- (Optional) Maven for build management

## 📋 Project layout

```
employee management system/
├─ pom.xml
├─ README.md
└─ src/main/java/employee/management/system/
   ├─ AddEmployee.java
   ├─ View_Employee.java
   ├─ UpdateEmployee.java
   ├─ RemoveEmployee.java
   ├─ Login.java
   ├─ Splash.java
   ├─ Main_class.java
   └─ conn.java
```

---

## ⚙️ Prerequisites

- JDK 8 or later
- MySQL Server (or compatible) running locally or accessible from the app
- (If using Maven) Maven 3.x
- Add the required external JARs to classpath (or use Maven dependencies shown below):
  - mysql-connector-java
  - jcalendar (toedter)
  - rs2xml (net.proteanit)

> Tip: Using an IDE (IntelliJ IDEA / Eclipse) is the easiest way to add the JARs and run the GUI.

---

## 🗄 Database setup

Create a database and the minimal tables used by the app. Example SQL:

```sql
CREATE DATABASE employee;
USE employee;

CREATE TABLE employee (
  empId VARCHAR(50) PRIMARY KEY,
  name VARCHAR(100),
  father_name VARCHAR(100),
  dob VARCHAR(50), -- stored as string by the UI (can be changed to DATE)
  salary VARCHAR(50),
  address TEXT,
  phone VARCHAR(30),
  email VARCHAR(100),
  education VARCHAR(50),
  designation VARCHAR(50),
  aadhar VARCHAR(50)
);

CREATE TABLE login (
  username VARCHAR(50) PRIMARY KEY,
  password VARCHAR(100) -- currently plaintext in the app; consider hashing
);

-- Example default user (change password immediately):
INSERT INTO login (username, password) VALUES ('admin','admin');
```

