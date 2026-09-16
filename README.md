# Starbucks-Customer-Analysis-SQL-
Find which hours generate the highest volume of orders: 
SELECT 
    SUBSTR(field4, 1, INSTR(field4, ':') - 1) AS order_hour,
    COUNT(field2) AS total_orders,
    ROUND(AVG(CAST(field15 AS NUMERIC)), 2) AS avg_spend
FROM starbucks_customer_ordering_patterns
WHERE field1 != 'customer_id'
GROUP BY order_hour
ORDER BY total_orders DESC;
