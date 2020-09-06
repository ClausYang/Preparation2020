# Chapter 22 使用视图

视图：虚拟的表，使用时只包含动态检索的数据

```mysql
CREATE VIEW productcustomers AS
SELECT cust_name, cust_contact, prod_id
FROM customers, orders,orderitems
WHERE customers.cust_id = orders.cust_id
AND orderitems.order_num = orders.order_num
```

查询类似于TABLE

```mysql
SELECT cust_name,cust_contact
FROM productcustomers
WHERE prod_id='TNT2'
```

视图可以过滤数据IS NOT NULL

```mysql
CREATE VIEW customeremaillist AS
SELECT cust_id,cust_name,cust_email
FROM customers
WHERE cust_email IS NOT NULL
```

