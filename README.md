# Project-234n

Input code: 

WITH query_1 as (

SELECT 
 customers.last_name as customers_last_name,
 customers.phone as customers_phone_number,
 company_orders.id as order_item_id
from customers
LEFT JOIN
company_orders
ON
company_orders.customer_id = customers.id
),

query_2 as (
SELECT
 order_items.product_id as order_item_id,
 company_products.name as product,
 suppliers.contact_name as supplier_contact_name

FROM order_items
LEFT JOIN
company_products
ON  company_products.id = order_items.product_id
LEFT JOIN
suppliers 
ON
suppliers.id = company_products.supplier_id

)
SELECT DISTINCT
query_1.customers_last_name,
query_1.customers_phone_number,
query_2.product,
query_2.supplier_contact_name
FROM query_1 JOIN query_2 
ON query_1.order_item_id = query_2.order_item_id


Output:
<img width="1201" alt="Screenshot 2024-01-27 at 12 13 49 PM" src="https://github.com/DizzyDagem1/Project-234/assets/87994132/ee7bd562-72ea-4e74-bbf8-798534d0a734">
