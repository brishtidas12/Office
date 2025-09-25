# Office
Create table Customers(
    -> customer_id INT(50) primary key,
    -> customer_name VARCHAR(50),
    -> customer_city VARCHAR(50)
    -> );

Create table Orders(
    -> order_id INT(50),
    -> order_date DATE,
    -> customer_id INT(50),
    -> order_amount DECIMAL(50)
    -> );

 Insert into Customers (customer_id, customer_name, customer_city) VALUES
    -> (01, 'Mr. Rajesh Singh', 'Delhi')
    -> (02, 'Ms. Kavita Sharma', 'Kolkata'),
    -> (03, 'Mr. Suresh Kumar', 'Chennai'),
    -> (04, 'Ms. Anjali Verma', 'Hyedrabad'),
    -> (05, 'Mr. Manoj Patel', 'Surat');

 Select * from Customers;
+-------------+-------------------+---------------+
| customer_id | customer_name     | customer_city |
+-------------+-------------------+---------------+
|           1 | Mr. Rajesh Singh  | Delhi         |
|           2 | Ms. Kavita Sharma | Kolkata       |
|           3 | Mr. Suresh Kumar  | Chennai       |
|           4 | Ms. Anjali Verma  | Hyedrabad     |
|           5 | Mr. Manoj Patel   | Surat         |
+-------------+-------------------+---------------+

  Insert into Orders (order_id, order_date, customer_id, order_amount) Values
    -> (001, '2025-04-01', 01, 10000.00),
    -> (002, '2025-05-01', 02, 15000.00),
    -> (003, '2025-05-10', 03, 10000.00),
    -> (004, '2025-06-15', 04, 18000.00),
    -> (005, '2025-07-11', 05, 20000.00);

 Select
    -> customer_id,
    -> count(order_id) as total_orders,
    -> sum(order_amount) as total_sales
    -> From Orders
    -> Group By customer_id;
+-------------+--------------+-------------+
| customer_id | total_orders | total_sales |
+-------------+--------------+-------------+
|           1 |            2 |       20000 |
|           2 |            1 |       15000 |
|           3 |            1 |       10000 |
|           4 |            1 |       18000 |
|           5 |            1 |       20000 |
+-------------+--------------+-------------+

Select
    -> customer_id,
    -> Avg(order_amount) as average_order_value
    -> From Orders
    -> Group By customer_id;
+-------------+---------------------+
| customer_id | average_order_value |
+-------------+---------------------+
|           1 |          10000.0000 |
|           2 |          15000.0000 |
|           3 |          10000.0000 |
|           4 |          18000.0000 |
|           5 |          20000.0000 |
+-------------+---------------------+

