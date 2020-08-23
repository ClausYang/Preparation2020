# Chapter 10 创建计算字段

拼接字段：Concat

```mysql
SELECT CONCAT(vend_name,'(',vend_country,')')
FROM vendors
ORDER BY vend_name
```

删除右边多余的空格：RTrim

```mysql
SELECT CONCAT(RTRIM(vend_name), '(', RTRIM(vend_country), ')')
FROM vendors
ORDER BY vend_name
```

使用别名：AS

```mysql
SELECT CONCAT(RTRIM(vend_name), '(', RTRIM(vend_country), ')') AS vend_title
FROM vendors
ORDER BY vend_name
```

执行算数计算

```mysql
SELECT prod_id, quantity,item_price, quantity*item_price AS expanded_price
FROM orderitems
WHERE order_num=20005;
```

