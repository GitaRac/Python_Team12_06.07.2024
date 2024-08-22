
#Relationships in SQLite
=========================
## What are relationships in SQLite?

In SQLite, relationships refer to the connections between tables in a database. These connections are established through common columns between tables, allowing you to link data across multiple tables.

## Types of relationships in SQLite

There are three main types of relationships in SQLite:

### One-to-One (1:1) relationships
In a 1:1 relationship, each row in one table is related to only one row in another table. For example, a customer table and an address table, where each customer has only one address.

### One-to-Many (1:N) relationships
In a 1:N relationship, each row in one table is related to multiple rows in another table. For example, a customer table and an orders table, where each customer can have multiple orders.

### Many-to-Many (M:N) relationships
In an M:N relationship, each row in one table is related to multiple rows in another table, and vice versa. For example, a products table and a categories table, where each product can belong to multiple categories, and each category can have multiple products.

## How to create relationships in SQLite?

To create relationships in SQLite, you need to define foreign key constraints between tables. A foreign key is a column in a table that references the primary key of another table.
Here is an example of how to create a 1:N relationship between a customers table and an orders table:
```sql
CREATE TABLE customers (
  id INTEGER PRIMARY KEY,
  name TEXT NOT NULL
);

CREATE TABLE orders (
  id INTEGER PRIMARY KEY,
  customer_id INTEGER NOT NULL,
  FOREIGN KEY (customer_id) REFERENCES customers (id)
);
```
In this example, the **customer_id column** in the **orders** table references the **id** column in the **customers** table, establishing a 1:N relationship between the two tables.

## How to query relationships in SQLite
To query relationships in SQLite, you can use the **JOIN** clause to combine data from multiple tables.
Here is an example of how to query the customers and orders tables to retrieve all orders for each customer:
```sql
SELECT customers.name, orders.id, orders.customer_id
FROM customers
JOIN orders ON customers.id = orders.customer_id;
```
This query will return a result set with the customer name, order ID, and customer ID for each order.

## Conclusion
In this tutorial, we covered the basics of relationships in SQLite, including the types of relationships and how to create and query them. By understanding relationships in SQLite, you can design more efficient and scalable databases for your applications.
```
