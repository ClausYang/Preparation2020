# Chapter 14 子查询

由内而外查询，先查询内部的

```mysql
SELECT cust_name,cust_contact
FROM customers
WHERE cust_id IN (SELECT cust_id
									FROM orders
									WHERE order_num IN (SELECT order_num
																			FROM orderitems
																			WHERE prod_id = 'TNT2')	)
```

计算字段的子查询

```mysql
SELECT cust_name,cust_state,
			(SELECT COUNT(*)
			FROM orders
			where orders.cust_id = customers.cust_id)	AS orders
FROM customers
ORDER BY cust_name
```

