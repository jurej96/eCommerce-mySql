# E-Commerce Database Project

Simple e-commerce database system managing products, categories, customers, and sales.

## Database Schema

- **categories**: `categoryID`, `categoryName`
- **products**: `productID`, `productName`, `categoryID`, `price`, `stock`
- **customers**: `customerID`, `firstName`, `lastName`, `eMail`
- **sales**: `saleID`, `customerID`, `productID`, `quantity`, `saleDate`

## Key Queries

### View Products and Stock
```sql
SELECT productName, price, stock FROM products;
Check Low Stock Items
sql


### SELECT productName, stock 
FROM products 
WHERE stock < 5;
Calculate Total Revenue
sql


### SELECT SUM(products.price * sales.quantity) AS totalRevenue
FROM sales
JOIN products ON sales.productID = products.productID;
Best Selling Products
sql


### SELECT p.productName, SUM(s.quantity) AS totalSold
FROM sales s
JOIN products p ON s.productID = p.productID
GROUP BY s.productID
ORDER BY totalSold DESC;
View Customer Purchases
sql


### SELECT c.firstName, p.productName, s.quantity, s.saleDate
FROM sales s
JOIN customers c ON s.customerID = c.customerID
JOIN products p ON s.productID = p.productID
WHERE c.customerID = 3;


###Implementation
Create tables
Insert sample data
Run analysis queries
