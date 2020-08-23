# Chapter 4 检索数据

检索单列:SELECT

```mysql
SELECT prod_name FROM products;
```

检索多列

```mysql
SELECT prod_name,prod_id,prod_price FROM products;
```

检索所有列

```mysql
SELECT * FROM products;
```

检索不同的行:DISTINCT

```mysql
SELECT DISTINCT vend_id FROM products;
```

限制结果：LIMIT限制长度

```mysql
SELECT prod_name FROM products LIMIT 5;
```

返回从行5开始的5行

```mysql
SELECT prod_name FROM products LIMIT 5,5(5 OFFSET 5);
```

完全限定的表名

```mysql
SELECT products.prod_name FROM products;
```



