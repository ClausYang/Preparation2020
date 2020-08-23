# Chapter 8 用通配符进行过滤

%：任何字符出现任意次数

```mysql
SELECT prod_id,prod_name
FROM products
WHERE prod_name LIKE 'jet%'
```

```mysql
SELECT prod_id,prod_name
FROM products
WHERE prod_name LIKE '%anvil%'
```

_：匹配单个字符

```mysql
SELECT prod_id,prod_name
FROM products
WHERE prod_name LIKE '_ ton anvil'
```

