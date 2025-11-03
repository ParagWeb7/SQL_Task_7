# SQL_Task_7
Task 7:Creating Views Objective: Learn to create and use views Tools :DB Browser for SQLite / MySQL Workbench Deliverables: View definitions and usage examples

1️⃣ Schema Setup
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    EmpName VARCHAR(100),
    Department VARCHAR(50),
    Salary DECIMAL(10,2)
);


CREATE TABLE Departments (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50),
    Location VARCHAR(50)
);

2️⃣ Insert Sample Data

INSERT INTO Employees VALUES (1, 'Amit', 'HR', 45000.00);
INSERT INTO Employees VALUES (2, 'Neha', 'IT', 60000.00);
INSERT INTO Employees VALUES (3, 'Ravi', 'IT', 70000.00);
INSERT INTO Employees VALUES (4, 'Kiran', 'Finance', 50000.00);
INSERT INTO Employees VALUES (5, 'Sita', 'HR', 40000.00);
INSERT INTO Departments VALUES (1, 'HR', 'Mumbai');
INSERT INTO Departments VALUES (2, 'IT', 'Pune');


3️⃣ Creating and Using Views

 CREATE VIEW EmployeeDepartmentView AS
SELECT EmpName, Department
FROM Employees;

SELECT * FROM EmployeeDepartmentView;

CREATE VIEW HighSalaryEmployees AS
SELECT EmpName, Department, Salary
FROM Employees
WHERE Salary > 50000;

SELECT * FROM HighSalaryEmployees;

CREATE VIEW EmployeeDetailsView AS
SELECT e.EmpName, e.Department, e.Salary, d.Location
FROM Employees e
JOIN Departments d ON e.Department = d.DeptName;

SELECT * FROM EmployeeDetailsView;


DROP VIEW HighSalaryEmployees;
