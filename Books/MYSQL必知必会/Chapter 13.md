# Chapter 13 分组数据

GROUP BY

```mysql
SELECT vend_id, COUNT(*) AS num_prods
FROM products
GROUP BY vend_id
```

过滤分组：使用HAVING，类似于WHERE，但是WHERE过滤行，HAVING过滤分组

```mysql
SELECT vend_id, COUNT(*) AS num_prods
FROM products
GROUP BY vend_id
HAVING COUNT(*)>2
```

混合使用：过滤出订单价格>10，订单数量大于等于2的订单

```mysql
SELECT vend_id, COUNT(*) AS num_prods
FROM products
WHERE prod_price>=10
GROUP BY vend_id
HAVING COUNT(*)>=2
```

GROUP BY和ORDER BY：检索订单价格>=50的订单号和总计订单价格

```mysql
SELECT order_num, SUM(item_price*quantity) AS ordertotal
FROM orderitems
GROUP BY order_num
HAVING SUM(item_price*quantity)>=50
ORDER BY ordertotal
```

