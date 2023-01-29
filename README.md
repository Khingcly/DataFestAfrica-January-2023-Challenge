# DataFestAfrica-January-2023-Challenge
I partook in the DataFestAfrica SQL January 2023 challenge 

The Problem

For this question you’ll need to use SQL. Follow this link https://www.w3schools.com/SQL/TRYSQL.ASP?FILENAME=TRYSQL_SELECT_ALL to access the data set required for the challenge. 
Please use queries to answer the following questions. 

Q1. How many orders were shipped by Speedy Express in total?      
SELECT Shippers.ShipperName, COUNT(*) AS Total_Orders
FROM Orders JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID 
WHERE Shippers.ShipperName = 'Speedy Express'
Answer = 54
![Q1](https://user-images.githubusercontent.com/96332895/215300572-3f70b8e0-3937-4f2f-9e8e-53fc7e22c4e1.jpg)

Q2. What is the last name of the employee with the most orders?   
SELECT Employees.LastName, COUNT(*) AS Total_Orders
FROM Orders
JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID 
GROUP BY LastName
ORDER BY Total_Orders DESC
LIMIT 1   
Answer = Peacock is 40
![Q2](https://user-images.githubusercontent.com/96332895/215300625-222c1df1-bf0b-4ae6-8f0b-739f9520aa13.jpg)

Q3. What product was ordered the most by customers in Germany?   
SELECT  Products.ProductName, OrderDetails.Quantity, Customers.Country
FROM Customers
JOIN Orders ON Customers.CustomerID = Orders.CustomerID
JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID
JOIN Products ON OrderDetails.ProductID = Products.ProductID
WHERE Country = 'Germany'
ORDER BY Quantity DESC
LIMIT 1   
Answer = Steeleye Stout 
![Q3](https://user-images.githubusercontent.com/96332895/215300655-2314fb44-6554-43a9-99d9-8157d049fdc3.jpg)

FInd attached a copy of the code file in docx   
[January Challenge (SQL).docx](https://github.com/Khingcly/DataFestAfrica-January-2023-Challenge/files/10528796/January.Challenge.SQL.docx)

