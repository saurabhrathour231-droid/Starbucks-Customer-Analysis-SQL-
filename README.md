# Starbucks-Customer-Analysis-SQL-
SQL analysis of Starbucks customer ordering patterns to identify spending trends ,  customer behaviour and purchasing patterns.
Most Popular & Highest Revenue Drink Categories : 
SELECT 
    field17 AS drink_category,
    COUNT(field2) AS items_sold,
    ROUND(SUM(CAST(field15 AS NUMERIC)), 2) AS total_revenue,
    ROUND(AVG(CAST(field15 AS NUMERIC)), 2) AS avg_order_value
FROM starbucks_customer_ordering_patterns
WHERE field1 != 'customer_id'
GROUP BY field17
ORDER BY total_revenue DESC;

