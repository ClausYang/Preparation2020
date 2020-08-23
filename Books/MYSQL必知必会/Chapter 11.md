# Chapter 11 使用数据处理函数

文本处理函数

```mysql
SELECT vend_name,UPPER(vend_name) AS vend_name_upcase
FROM vendors
ORDER BY vend_name
```

Soundex()：根据发音联系数据

日期和时间处理函数

**在取日期的时候记得用日期函数**

```mysql
SELECT cust_id, order_num
FROM orders
WHERE DATE(order_date) = '2005-09-01'
```

ex:匹配9月份的订单

```mysql
SELECT cust_id, order_num
FROM orders
WHERE DATE(order_date) BETWEEN '2005-09-01' AND '2005-09-30'
```

```mysql
SELECT cust_id, order_num
FROM orders
WHERE YEAR(order_date)=2005 AND MONTH(order_date)=9
```

数值处理函数