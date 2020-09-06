# Chapter 21 创建和操纵表

```mysql
CREATE TABLE customers
(
cust_id int NOT NULL AUTO_INCREMENT,
cust_name char(50) NOT NULL DEFAULT 1,
  PRIMARY KEY (cust_id)
)ENGINE=INNODB
```

NOT NULL不允许空值，NULL允许空值

AUTO_INCREMENT表示自动增量

DEFAULT 1表示设置自动

### 引擎的选择

InnoDB：可靠的事务处理，不支持全文本搜索

MEMORY：数据存储在内存，速度很快，适合临时表

MyISAM：支持全文本搜索，不支持事务处理

### 更新表

ALTER TABLE ADD增加一列

DROP 删除一列

### 删除表

DROP TABLE

### 重命名表

RENAME TABLE x TO xx