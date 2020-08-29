# Chapter 12 汇总数据

AVG()：获取平均数字

```mysql
SELECT AVG(prod_price) AS avg_price
FROM products
```

```mysql
SELECT AVG(prod_price) AS avg_price
FROM products
WHERE vend_id=1003
```

COUNT()：计数

```mysql
-- *表示对所有计数
SELECT COUNT(*) AS num_cust
FROM customers
```

```mysql
-- 只对有email的计数
SELECT COUNT(cust_email) AS num_cust
FROM customers
```

MAX()：返回最大值

```mysql
SELECT MAX(prod_price) AS max_price
FROM products
```

MIN()：返回最小值

SUM()：返回列值和

```mysql
-- 表示物品总价
SELECT SUM(item_price*quantity) AS total_price
FROM orderitems
WHERE order_num = 20005
```

DISTINCT可以在使用聚集函数时只用不重复的数据