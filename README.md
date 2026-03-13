
---

# Student Information System (Java + MySQL)

## Project Description

This project is a **Simple Student Information System (SIS)** developed using **Java, MySQL, and NetBeans**. The system allows users to manage student records through a graphical user interface (GUI). It performs basic **CRUD operations (Create, Read, Update, Delete)** and connects a Java application to a MySQL database using JDBC.

The purpose of this project is to demonstrate how a Java application can interact with a database while providing a simple interface for managing data.

---

# Objectives

* Connect a Java application to a MySQL database
* Implement CRUD operations
* Build a simple GUI using Java Swing
* Organize project code using classes and database access objects (DAO)

---

# Technologies Used

* **Java (JDK 8 or later)**
* **NetBeans IDE**
* **MySQL Workbench**
* **MySQL JDBC Driver (Connector/J)**
* **Java Swing (GUI)**

---

# System Features

The system allows users to:

* Add a new student
* View all student records
* Update student information
* Delete student records
* Store student data in a MySQL database

---

# Database Setup

## 1. Create Database

Run the following SQL command in MySQL Workbench:

```sql
CREATE DATABASE student_information_system;
```

---

## 2. Create Table

```sql
USE student_information_system;

CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    age INT,
    email VARCHAR(100)
);
```

---

# Project Structure

```
StudentInformationSystem
│
├── DBConnection.java
├── Student.java
├── StudentDAO.java
├── MainFrame.java
└── mysql-connector-java.jar
```

### File Descriptions

**DBConnection.java**

* Handles the connection between Java and MySQL.

**Student.java**

* Model class representing a student object.

**StudentDAO.java**

* Contains CRUD operations for the student table.

**MainFrame.java**

* The graphical user interface built using Java Swing.

---

# Database Connection Code

Example connection class:

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DBConnection {

    private static Connection connection = null;

    public static Connection getConnection() {

        try {

            if(connection == null){

                Class.forName("com.mysql.cj.jdbc.Driver");

                connection = DriverManager.getConnection(
                        "jdbc:mysql://localhost:3306/student_information_system",
                        "root",
                        "your_password"
                );

            }

        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        }

        return connection;
    }
}
```

Replace **your_password** with your MySQL password.

---

# CRUD Operations

## Create (Insert Student)

Adds a new student record to the database.

```java
INSERT INTO students (first_name, last_name, age, email)
VALUES (?, ?, ?, ?)
```

---

## Read (View Students)

Retrieves all student records from the database.

```java
SELECT * FROM students
```

---

## Update

Updates the selected student's information.

```java
UPDATE students
SET first_name=?, last_name=?, age=?, email=?
WHERE student_id=?
```

---

## Delete

Deletes a student using the student ID.

```java
DELETE FROM students
WHERE student_id=?
```

---

# GUI Features

The Java Swing interface includes:

* Text fields for student information
* Table to display student records
* Buttons for:

  * Add
  * Update
  * Delete
  * Refresh

---

# How to Run the Project

1. Install **NetBeans IDE**
2. Install **MySQL Workbench**
3. Create the database and table
4. Add **MySQL Connector/J** to the project libraries
5. Open the project in NetBeans
6. Update the database password in `DBConnection.java`
7. Run the project

---

# Evaluation Criteria

The project will be evaluated based on:

* Successful database connection
* Working CRUD operations
* Functional GUI
* Organized code structure

---
