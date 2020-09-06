# Chapter 20 更新和删除数据

UPDATE：更新多行只需要一个SET，删除即设置为NULL

```mysql
UPDATE customers
SET cust_name = 'The Fudds',
		cust_email = 'elmer@fudd.com'
WHERE cust_id=10005
```

删除DELETE

```mysql
DELETE FROM customers
WHERE cust_id=10006
```

