# Chapter 16 创建高级联结

起别名

```mysql
SELECT CONCAT(vend_name,'(',vend_country,')') AS vend_title
FROM vendors
ORDER BY vend_name
```

```mysql
SELECT cust_name,cust_contact
FROM customers AS c,orders AS o,orderitems as oi
WHERE c.cust_id = o.cust_id
AND oi.order_num = o.order_num
AND prod_id = 'TNT2'
```

自联结：使用表别名可以用来处理多次出现的表名

下面两个例子结果是相同的，一个使用子查询，一个使用自连接

```mysql
SELECT prod_id,prod_name
FROM products
WHERE vend_id = (SELECT vend_id
									FROM products
									WHERE prod_id = 'DTNTR')
```

```mysql
SELECT p1.prod_name,p1.prod_id
FROM products AS p1,products AS p2
WHERE p1.vend_id = p2.vend_id
AND p2.prod_id = 'DTNTR'
```

自然联接：排除多次出现，使每个列只返回一次

外部联结：包含在相关表中没有关联行的行

其中left和right分别指定需要放出哪边表中的所有行

```mysql
SELECT customers.cust_id, orders.order_num
FROM customers LEFT OUTER JOIN orders
ON customers.cust_id = orders.cust_id
```

结合聚集函数进行联结

```mysql
SELECT customers.cust_name,customers.cust_id,COUNT(orders.order_num) AS num_ord
-- 这里使用left为了让customers全部行都显示出来
FROM customers LEFT OUTER JOIN orders
ON customers.cust_id = orders.cust_id
GROUP BY customers.cust_id
```

