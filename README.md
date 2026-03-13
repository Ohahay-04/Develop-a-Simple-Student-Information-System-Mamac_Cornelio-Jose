# Develop-a-Simple-Student-Information-System-Mamac_Cornelio-Jose 
This README file provides a comprehensive guide to the Student Information System (SIS) project. It covers everything from system requirements to implementation steps, based on the provided activity instructions.
Student Information System (SIS)Project OverviewThe Student Information System (SIS) is a Java-based desktop application designed to manage student records efficiently. It utilizes a MySQL database for persistent storage and Java Swing for a user-friendly graphical interface. This project demonstrates the practical application of CRUD (Create, Read, Update, Delete) operations in a database-driven environment.

Key FeaturesAdd Student:
Register new students with their first name, last name, age, and email.
View Students: Retrieve and display a comprehensive list of all registered students from the database.
Update Records: Modify existing student information based on their unique ID.
Delete Records: Remove student entries from the system.

Technical RequirementsTo run or develop this system, ensure your environment meets the following specifications:Software & VersionsIDE: NetBeans.Database: MySQL Workbench (Version 8.0.25 or 8.0.11 recommended).Java: Java 8 or later
.Essential DependenciesMySQL JDBC Driver (Connector/J):
Required for connecting the Java application to the MySQL server.
Database ConfigurationThe system relies on a MySQL table named students within the student_information_system database.
Table SchemaFieldTypeDescriptionstudent_idINTPrimary Key (Auto-incremented) first_nameVARCHAR(100)Student's First Name last_nameVARCHAR(100)Student's Last Name ageINTStudent's Age emailVARCHAR(100)Student's Email Address Implementation Guide1. Database SetupInitialize the database: CREATE DATABASE student_information_system;.Create the students table using the schema provided above.2. Project ConfigurationCreate a new Java Application project in NetBeans named StudentInformationSystem.Add the mysql-connector-java-x.x.xx.jar to your project's Libraries.3. Core Java ClassesDBConnection.java: Handles the connection to MySQL using your root credentials.Student.java: A model class representing a student object.StudentDAO.java: The "Data Access Object" containing the logic for addStudent, getAllStudents, updateStudent, and deleteStudent.4. UI DevelopmentUse the NetBeans GUI Builder to design a frame with the following components:Input Fields: Text fields for student details.Action Buttons: Buttons labeled "Add", "Update", and "Delete" with attached Action Listeners to trigger the DAO methods.Display Table: A JTable to show real-time database content.
