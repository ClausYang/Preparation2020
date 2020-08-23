# Chapter 6 过滤数据

条件过滤：WHERE

```mysql
SELECT prod_name,prod_price
FROM products
WHERE prod_price=2.50
```

WHERE子句操作符

| 操作符  |       说明       |
| :-----: | :--------------: |
|    =    |       等于       |
|   <>    |      不等于      |
|   !=    |      不等于      |
|    <    |       小于       |
|   <=    |     小于等于     |
| BETWEEN | 在指定的两值中间 |

检查单个值

```mysql
SELECT prod_name,prod_price
FROM products
WHERE prod_name='fuses`
```

不匹配检查：<>

```mysql
SELECT prod_name,vend_id
FROM products
WHERE vend_id<>1003
```

范围值检查：BETWEEN

```mysql
SELECT prod_name,prod_price
FROM products
WHERE prod_price BETWEEN 5 AND 10;
```

空值检查

```mysql
SELECT prod_name
FROM products
WHERE prod_price IS NULL;
```



