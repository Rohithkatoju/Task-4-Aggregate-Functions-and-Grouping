# Task-4-Aggregate-Functions-and-Grouping

sales

sale_id	product_id	amount	sale_date
1	101	500	2024-05-01
2	102	300	2024-05-01
3	101	450	2024-05-02

products

product_id	product_name
101	Laptop
102	Monitor

-- Above table is created from the bot, as I requested a table for the this specific task


-- 1. Total Sales Amount

select 
    sum(amount) as total_sales
from
    sales;


-- 2. Average Sale Amount per Product

select 
    product_id, avg(amount) as avg_sale
from
    sales
group by product_id;


-- 3. Total Sales per Product with Product Names

select 
    p.product_name, sum(s.amount) as total_sales
from
    sales s
        join
    products p on s.product_id = p.product_id
group p.product_name;


-- 4. Count of Sales per Day

select 
    sale_date, count(*) as total_sales_count
from
    sales
group by sale_date;


-- 5. Filter Groups Using HAVING
-- Find products whose total sales are more than 800

select 
    product_id, sum(amount) as total_sales
from
    sales
group by product_id
having sum(amount) > 800;


-- Outcome: Performed multiple quries on Aggregations and using Group by cluase....
