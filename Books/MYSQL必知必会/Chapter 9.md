# Chapter 9 正则表达式

基本字符匹配

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '1000'
ORDER BY prod_name;
```

.：匹配任意一个字符

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '.000'
ORDER BY prod_name;
```

OR匹配：|

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '1000|2000'
ORDER BY prod_name;
```

匹配几个字符之一：[]

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '[123] ton'
ORDER BY prod_name;
```

匹配范围

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '[1-5] ton'
ORDER BY prod_name;
```

匹配特殊字符：\\\作为前导

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '\\.'
ORDER BY prod_name;
```

定位符：^ $

```mysql
SELECT prod_name
FROM products
WHERE prod_name REGEXP '^[0-9\\.]'
ORDER BY prod_name;
```

