                                                         #Task-5(SQL Joins)# CUSTOMER-AND-ORDERS--
# CUSTOMER-AND-ORDERS--
                                                   
This project demonstrates how to create two related tables and apply different types of SQL JOINs—INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL OUTER JOIN—to query related data effectively.

📁 Project Overview
In this SQL practice project, we:

Create two related tables: Customers and Orders
Establish a foreign key relationship between them
Use various SQL JOINs to retrieve data across these tables
This setup is useful for understanding relational databases and how different JOIN operations behave with matching and non-matching records.

This project is part of my learning and internship submission, aimed at demonstrating my understanding of database design concepts.

📌 Tables:
Customers
Orders
``` 🧾SQL Script
Creating the data
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(50),
    City VARCHAR(50)
);
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    Product VARCHAR(50),
    Amount DECIMAL(10, 2),
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
-- Insert into Customers
INSERT INTO Customers (CustomerID, Name, Email) VALUES
(1, 'Prajjawal', 'prajjwalkushwaha26@gmail.com'),
(2, 'Pranshu', 'pranshu29@gmail.com'),
(3, 'Mayank', 'mayank@gmail.com');

-- Insert into Orders
INSERT INTO Orders (OrderID, CustomerID, Product, OrderDate, Amount) VALUES
(101, 1, 'Product A', '2025-05-03', 500.00),
(102, 1, 'Product B', '2025-05-04', 1500.00),
(103, 3, 'Product C', '2025-05-06', 2000.00);
🔄 SQL JOIN Queries
1- INNER JOIN

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;


2- LEFT JOIN

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;

3- RIGHT JOIN

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;

4- FULL JOIN


SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID

UNION

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;


