# Chapter 17 组合查询

UNION：连接两个查询

```mysql
SELECT vend_id,prod_id,prod_price
FROM products
WHERE prod_price<=5
UNION
SELECT vend_id,prod_id,prod_price
FROM products
WHERE vend_id IN (1001,1002)
```

UNION有自动去掉重复行的功能，如果需要显示重复则UNION ALL

UNION中ORDER BY只在最后使用一次，且对所有的查询都生效

