# Chapter 19 插入数据

INSERT：插入数据

```mysql
INSERT INTO customers
VALUES(NULL,'Pep E. LaPew','100 Main Street','Los Angeles','CA',
'90046','USA',NULL,NULL)
```

上述的插入语句更看重次序，很不安全，更安全的如下，写上每一列的名字，这样就会一一对应上

```mysql
INSERT INTO customers(cust_name,
                     cust_address)...
VALUES(NULL,'Pep E. LaPew','100 Main Street','Los Angeles','CA',
'90046','USA',NULL,NULL)
```

插入多行：用分号结束，每次都插入 或者一次INSERT后面有多个待插入数据

插入检索出的数据INSERT SELECT：把select出来的东西插入到insert into的东西里面去

```mysql
INSERT INTO xxx
SELECT xxx
FROM xxx
```

