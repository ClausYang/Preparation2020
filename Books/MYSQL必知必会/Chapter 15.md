# Chapter 15 联结表

外键：某个表中的一列，作为其他表的主键存在

通过where正确连接

```mysql
SELECT vend_name,prod_name,prod_price
FROM vendors,products
WHERE vendors.vend_id = products.vend_id
ORDER BY vend_name,prod_name
```

内部联结

```mysql
SELECT vend_name,prod_name,prod_price
FROM vendors INNER JOIN products
ON vendors.vend_id = products.vend_id
```

联结多个表：选择出编号为20005的产品

```mysql
SELECT prod_name,vend_name,prod_price,quantity
FROM products,vendors,orderitems
WHERE products.vend_id = vendors.vend_id
AND orderitems.prod_id = products.prod_id
AND order_num = 20005
```



