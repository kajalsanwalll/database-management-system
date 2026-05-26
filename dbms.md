# DBMS & SQL Notes

---

# Database & DBMS

## Database
A **Database** is a collection of related data that represents some aspect of the real world.

Example:
- Student database
- Banking database
- Hospital database

---

## DBMS (Database Management System)

A **DBMS** is software used to store, retrieve, and manage data securely and efficiently.

It acts as an interface between:
- User
- Application
- Database

### Problems Solved by DBMS
1. Data redundancy and inconsistency
2. Difficulty in accessing data
3. Data isolation
4. Integrity problems
5. Atomicity problems
6. Concurrent access issues
7. Security problems

---

# ER Model (Entity Relationship Model)

An **ER Diagram** represents the logical structure of a database graphically.

## Components of ER Diagram
- Entity Set
- Attributes
- Relationship Set

---

# Entity Set

An entity set is a collection of similar entities.

## Strong Entity Set
- Has a primary key
- Can uniquely identify entities

Example:
```text
Student(Roll_No, Name)
Roll_No is the primary key.
Weak Entity Set
Does not have a primary key
Uses a partial key called Discriminator
Relationship
A relationship defines association among entities.
Types of Relationships
Type	Description
Unary	One entity set participates
Binary	Two entity sets participate
Ternary	Three entity sets participate
N-ary	N entity sets participate
Cardinality Constraints
One-to-One (1:1)
One entity is related to at most one entity of another set.
One-to-Many (1:M)
One entity in A can relate to many entities in B.
Many-to-One (M:1)
Many entities in A can relate to one entity in B.
Many-to-Many (M:N)
Many entities in A relate to many entities in B.
Attributes
Attributes describe properties of entities.
Types of Attributes
Attribute Type	Description	Example
Simple	Cannot be divided further	Age
Composite	Can be divided	Name, Address
Multi-valued	Multiple values allowed	Phone Number
Derived	Derived from other attributes	Age from DOB
Key Attribute	Uniquely identifies entity	Roll No
Constraints
Constraints ensure correctness of data.
Types of Constraints
Domain Constraint
Defines valid values for an attribute.
Tuple Uniqueness Constraint
All tuples in a relation must be unique.
Key Constraint
Primary key values:
Must be unique
Cannot be NULL
Entity Integrity Constraint
Primary key cannot contain NULL values.
Referential Integrity Constraint
Foreign key values must:
Exist in referenced table
Or be NULL
Keys in DBMS
Super Key
A set of attributes that uniquely identifies tuples.
Candidate Key
Minimal super key.
Primary Key
Chosen candidate key.
Properties:
Unique
NOT NULL
Alternate Key
Candidate keys not selected as primary key.
Foreign Key
Attribute referencing primary key of another table.
Composite Key
Primary key made using multiple attributes.
Unique Key
Must contain unique values
Can contain NULL
Functional Dependency
A functional dependency:
A → B
means:
If two tuples have same value of A, then they must have same value of B.
Types of Functional Dependency
Trivial Functional Dependency
X → Y where Y ⊆ X
Example:
AB → A
Non-Trivial Functional Dependency
X → Y where Y ⊄ X
Example:
A → B
Normalization
Normalization reduces:
Redundancy
Inconsistency
Normal Forms
First Normal Form (1NF)
Atomic values only
No multi-valued attributes
Second Normal Form (2NF)
Requirements:
Must be in 1NF
No partial dependency
Third Normal Form (3NF)
Requirements:
Must be in 2NF
No transitive dependency
BCNF (Boyce-Codd Normal Form)
For every non-trivial FD:
A → B
A must be a super key.
ACID Properties
Atomicity
Either complete transaction happens or none.
Consistency
Database remains valid before and after transaction.
Isolation
Concurrent transactions should not affect each other.
Durability
Committed changes remain permanent.
SQL
SQL = Structured Query Language
Used for:
Storing data
Manipulating data
Retrieving data
Types of SQL Commands
DDL (Data Definition Language)
Command	Purpose
CREATE	Create database/table
ALTER	Modify structure
DROP	Delete object
TRUNCATE	Remove all rows
RENAME	Rename object
DML (Data Manipulation Language)
Command	Purpose
SELECT	Retrieve data
INSERT	Insert data
UPDATE	Modify data
DELETE	Delete data
MERGE	Insert/update
DCL (Data Control Language)
Command	Purpose
GRANT	Give permissions
REVOKE	Remove permissions
TCL (Transaction Control Language)
Command	Purpose
COMMIT	Save transaction
ROLLBACK	Undo transaction
SAVEPOINT	Create rollback point
SQL Commands
SELECT
SELECT column1, column2
FROM table_name;
Select all columns:
SELECT * FROM table_name;
SELECT DISTINCT
SELECT DISTINCT Country
FROM Customers;
WHERE Clause
SELECT *
FROM Customers
WHERE Country = 'Mexico';
Operators
Operator	Meaning
=	Equal
>	Greater than
<	Less than
>=	Greater than or equal
<=	Less than or equal
<>	Not equal
ORDER BY
SELECT *
FROM Customers
ORDER BY Country ASC;
Descending order:
SELECT *
FROM Customers
ORDER BY Country DESC;
INSERT INTO
INSERT INTO Customers(CustomerName, City)
VALUES('Kajal', 'Delhi');
UPDATE
UPDATE Customers
SET City='Mumbai'
WHERE CustomerID=1;
DELETE
DELETE FROM Customers
WHERE CustomerID=1;
Delete all rows:
DELETE FROM Customers;
Aggregate Functions
MIN()
SELECT MIN(Price)
FROM Products;
MAX()
SELECT MAX(Price)
FROM Products;
COUNT()
SELECT COUNT(*)
FROM Products;
AVG()
SELECT AVG(Price)
FROM Products;
SUM()
SELECT SUM(Quantity)
FROM OrderDetails;
SQL Joins
INNER JOIN
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
LEFT JOIN
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
RIGHT JOIN
SELECT Orders.OrderID, Employees.LastName
FROM Orders
RIGHT JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID;
FULL OUTER JOIN
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
GROUP BY
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
HAVING
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
CREATE DATABASE
CREATE DATABASE CollegeDB;
CREATE TABLE
CREATE TABLE Students (
    RollNo INT,
    Name VARCHAR(50),
    Age INT
);
ALTER TABLE
Add Column
ALTER TABLE Students
ADD Email VARCHAR(100);
Drop Column
ALTER TABLE Students
DROP COLUMN Email;
Modify Column
ALTER TABLE Students
MODIFY COLUMN Age BIGINT;