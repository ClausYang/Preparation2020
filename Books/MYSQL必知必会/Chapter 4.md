# Chapter 4 检索数据

检索单列:SELECT

`SELECT prod_name FROM products;`

检索多列

`SELECT prod_name,prod_id,prod_price FROM products;`

检索所有列

`SELECT * FROM products;`

检索不同的行:DISTINCT

`SELECT DISTINCT vend_id FROM products;`

限制结果：LIMIT限制长度

`SELECT prod_name FROM products LIMIT 5;`

`SELECT prod_name FROM products LIMIT 5,5（5 OFFSET 5）;`返回从行5开始的5行

完全限定的表名

`SELECT products.prod_name FROM products;`