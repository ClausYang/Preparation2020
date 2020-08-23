# Chapter 5 排序检索数据

排序数据

`SELECT prod_name
FROM products
ORDER BY prod_name;`

按多个列排序：ORDER BY多个列按顺序排序

`SELECT prod_id,prod_price,prod_name
FROM products
ORDER BY prod_price,prod_name;`

指定排序方向：DESC降序

`SELECT prod_id,prod_price,prod_name
FROM products
ORDER BY prod_price DESC;`

多个列排序降序：此时第二列没有指定仍然升序

`SELECT prod_id,prod_price,prod_name
FROM products
ORDER BY prod_price DESC,prod_name;`

找到最大（小）值：ORDER BY和LIMIT结合

`SELECT prod_id,prod_price,prod_name
FROM products
ORDER BY prod_price DESC
LIMIT 1;`

