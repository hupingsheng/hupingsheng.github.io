---
title: MYSQL1
categories:
  - db
  - mysql
author: hps
date: 2022-08-15
---

本文通过对于常见面试题的整理归纳，

<!-- more -->

## 第三章 基本的 SELECT 语句

### 3.基本的 SELECT 语句

#### 3.1 SELECT ... FROM

1. 选择全部列

```sql
SELECT *
FROM employees
```

![image-20220629174604525](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629174604525.png)

2. 选择特定的列

```sql
SELECT  employee_id,first_name
FROM employees;
```

![image-20220629175656142](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629175656142.png)

#### 3.2 列的别名

- 重命名一个列
- 便于计算

- 紧跟列名，也可以在列名和别名之间加入关键字`AS`，别名建议使用双引号" "

```sql
SELECT last_name AS "姓氏",commission_pct "奖金率"
FROM employees;
```

![image-20220629180434829](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629180434829.png)

```sql
SELECT last_name "Name", salary*12 "Annual Salary"
FROM employees;
```

![image-20220629181455186](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629181455186-16565010227836.png)

#### 3.3 去除重复行

```sql
SELECT DISTINCT department_id
FROM employees;
```

![image-20220629182258357](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629182258357-16565009551775.png)

> **补充**
>
> ```sql
> SELECT salary,DISTINCT department_id,
> FROM employees;
> ```
>
> 报错
>
> **salary 是 107 行，DISTINCT department_id, 是 12 行，左右无法组合**
>
> ```sql
> SELECT DISTINCT department_id,salary   #不会报错，将department_id,salary作为一个组合，筛选结果中，这个组合不会重复
> FROM employees;
> ```
>
> ![image-20220629183011011](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629183011011-16564986131301-16564987994882.png)

#### 3.4 空值参与运算

1. 空值：NULL
2. null 不等于 0，可以理解为“不知道”

![image-20220629184753487](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629184753487.png)

3. 空值运算规则：所有运算符或列值遇到 null 值，运算的结果都为 null

```sql
SELECT employee_id,salary,commission_pct,
12 * salary * (1 + commission_pct) "annual_sal"
FROM employees;
```

![image-20220629185533015](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629185533015-16565001344293.png)

#### 3.5 着重号

- 当表中的字段、表名等和保留字、数据库系统或常用方法冲突，用着重号避免

```sql
#表名ORDER 和 排序ORDER关键字重合，这个语句执行错误
SELECT * FROM ORDER;   #报错

SELECT * FROM `ORDER`;  #正确的
```

### 4.显示表结构

使用`DESC`命令，表示表结构。

```sql
DESC employees;
```

![image-20220629193555526](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629193555526.png)

其中，各个字段的含义分别解释如下：

- Field：表示字段名称。
- Type：表示字段类型，这里 barcode、goodsname 是文本型的，price 是整数类型的。
- Null：表示该列是否可以存储 NULL 值。
- Key：表示该列是否已编制索引。PRI 表示该列是表主键的一部分；UNI 表示该列是 UNIQUE 索引的一 部分；MUL 表示在列中某个给定值允许出现多次。
- Default：表示该列是否有默认值，如果有，那么值是多少。
- Extra：表示可以获取的与给定列有关的附加信息，例如 AUTO_INCREMENT 等。

### 5.过滤条件

```sql
SELECT 字段1,字段2
FROM 表名
WHERE 过滤条件
```

- 使用 WHERE 子句，将不满足条件的行过滤掉

- **WHERE 子句紧随 FROM 子句**

```sql
SELECT employee_id, last_name, job_id, department_id
FROM employees
WHERE department_id = 90 ;
```

![image-20220629203719692](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629203719692.png)

## 第四章 运算符

### 1. 算术运算符

算术运算符主要用于数学运算，其可以连接运算符前后的两个数值或表达式，对数值或表达式进行加 （+）、减（-）、乘（\*）、除（/）和取模（%）运算。

![image-20220629205550065](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629205550065.png)

```sql
#计算出员工的年基本工资
SELECT employee_id,salary,salary * 12 AS annual_sal
FROM employees;
```

```sql
#筛选出employee_id是偶数的员工
SELECT * FROM employees
WHERE employee_id MOD 2 = 0;
```

### 2. 比较运算符

- 比较运算符用来对表达式左边的操作数和右边的操作数进行比较，比较的结果为真则返回 1，比较的结果 为假则返回 0，其他情况则返回 NULL。

- 比较运算符经常被用来作为 SELECT 查询语句的**条件**来使用，返回符合条件的结果记录。

![image-20220629210003730](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629210003730.png)

```sql
#查询salary=10000，注意在Java中比较是==
SELECT employee_id,salary FROM employees WHERE salary = 10000;
```

1. 符号运算符 =、!=、>、>=、<、<=
2. 空运算符 IS NULL
3. 非空运算符　 IS NOT NULL

4. 最小值运算符

5. 最大值运算符

6. BETWEEN ... AND ... 运算符

7. IN 运算符

8. NOT IN 运算符

9. LIKE 运算符

​ LIKE 运算符主要用来**匹配字符串**，通常用于模糊匹配，如果满足条件则返回 1，否则返回 0。如果给定的值或者匹配条件为 NULL，则返回结果为 NULL。

```sql
“%”：匹配0个或多个字符。（任意字符）
“_”：只能匹配一个字符。
```

### 3.逻辑运算符

![image-20220629212601958](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629212601958.png)

### 4.位运算符

### 练习

1. 选择工资不在 5000 到 12000 的员工的姓名和工资

   ```sql
   SELECT first_name, salary
   FROM employees
   WHERE salary NOT BETWEEN 5000 AND 12000;
   ```

2. 选择在 20 或 50 号部门工作的员工姓名和部门号

   ```sql
   SELECT last_name,department_id
   FROM employees
   WHERE department_id=20 OR department_id=50;

   SELECT last_name,department_id
   FROM employees
   WHERE department_id IN(20,50);
   ```

3. 选择公司中没有管理者的员工姓名及 job_id

   ```sql
   SELECT last_name,job_id
   FROM employees
   WHERE manager_id IS NULL;
   ```

4. 选择公司中有奖金的员工姓名，工资和奖金级别

   ```sql
   SELECT last_name,salary,commission_pct
   FROM employees
   WHERE commission_pct IS NOT NULL;
   ```

5. 选择员工姓名的第三个字母是 a 的员工姓名

   ```sql
   SELECT last_name
   FROM employees
   WHERE last_name LIKE "__a%"
   ```

6. 选择姓名中有字母 a 和 k 的员工姓名

   ```sql
   SELECT last_name
   FROM employees
   WHERE last_name LIKE "%a%k%" OR last_name LIKE "%k%a%";
   ```

7. 显示出表 employees 表中 first_name 以 'e'结尾的员工信息

   ```sql
   SELECT *
   FROM employees
   WHERE first_name LIKE "%e";
   ```

8. 显示出表 employees 部门编号在 80-100 之间的姓名、工种

   ```sql
   SELECT last_name,job_id
   FROM employees
   WHERE department_id BETWEEN 80 AND 100;
   ```

9. 显示出表 employees 的 manager_id 是 100,101,110 的员工姓名、工资、管理者 id

   ```sql
   SELECT last_name,salary,manager_id
   FROM employees
   WHERE manager_id IN(100,101,110);
   ```

## 第五章 排序和分页

### 1.排序数据

1.1 排序规则

- 使用 ORDER BY 子句排序

  - ==ASC（ascend）: 升序（默认）==

  - ==DESC（descend）:降序==

- ==ORDER BY 子句在 SELECT 语句的结尾==

  1.2 单列排序

```sql
SELECT last_name, job_id, department_id, hire_date
FROM employees
ORDER BY hire_date ;
```

![image-20220629220253282](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629220253282.png)

```sql
SELECT last_name, job_id, department_id, hire_date
FROM employees
ORDER BY hire_date DESC ;
```

![image-20220629220425824](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629220425824.png)

1.3 多列排序

```sql
SELECT last_name, department_id, salary
FROM employees
ORDER BY department_id, salary DESC;
```

![image-20220629220942832](http://cdn.hupingsheng.com/img/MySql/selectimage-20220629220942832.png)

- 可以使用不在 SELECT 列表中的列排序。
- 在对多列进行排序的时候，首先排序的第一列必须有相同的列值，才会对第二列进行排序。如果第 一列数据中所有值都是唯一的，将不再对第二列进行排序。

### 2. 分页

2.1 背景

背景 1：查询返回的记录太多了，查看起来很不方便，怎么样能够实现分页查询呢？

背景 2：表里有 4 条数据，我们只想要显示第 2、3 条数据怎么办呢？

2.2 实现规则

- 分页原理 所谓分页显示，就是将数据库中的结果集，一段一段显示出来需要的条件。
- MySQL 中使用 LIMIT 实现分页

- 分页

  ```sql
  LIMIT [位置偏移量,] 行数
  ```

- 举例

  ```sql
  --前10条记录：
  SELECT * FROM 表名 LIMIT 0,10;
  或者
  SELECT * FROM 表名 LIMIT 10;
  --第11至20条记录：
  SELECT * FROM 表名 LIMIT 10,10;
  --第21至30条记录：
  SELECT * FROM 表名 LIMIT 20,10;
  ```

- 分页显式公式：（当前页数-1）\*每页条数，每页条数

  ```sql
  SELECT * FROM table
  LIMIT(PageNo - 1)*PageSize,PageSize;
  ```

- **注意：LIMIT 子句必须放在整个 SELECT 语句的最后！**
- 使用 LIMIT 的好处

​ 约束返回结果的数量可以 `减少数据表的网络传输量` ，也可以`提升查询效率`。如果我们知道返回结果只有 1 条，就可以使用`LIMIT 1`，告诉 SELECT 语句只需要返回一条记录即可。这样的好处就是 SELECT 不需 要扫描完整的表，只需要检索到一条符合条件的记录即可返回。

### 练习

1. 选择工资不在 8000 到 17000 的员工的姓名和工资，按工资降序，显示第 21 到 40 位置的数据

```sql
SELECT last_name,salary
FROM employees
WHERE salary NOT BETWEEN 8000 AND 17000
ORDER BY salary DESC
LIMIT 20,20;
```

2. 查询邮箱中包含 e 的员工信息，并先按邮箱的字节数降序，再按部门号升序

```sql
SELECT *
FROM employees
WHERE email LIKE "%e%"
ORDER BY LENGTH(email) DESC,department_id;
```

## 第六章 多表查询（重难点）

### 1.引入多表连接

**背景**：查询的多个字段不在一张表中

多表查询，也称为**关联查询**，指两个或更多个表一起完成查询操作。

前提条件：这些一起查询的表之间是有关系的（一对一、一对多），它们之间一定是有关联字段，这个 关联字段可能建立了外键，也可能没有建立外键。比如：员工表和部门表，这两个表依靠“部门编号”进 行关联。

![image-20220630100453917](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630100453917.png)

需求：查询每个员工的 id 和部门名称

```sql
#错误实现方式：每个员工与每个部门都匹配了一次，不符合实际情况
SELECT employee_id,department_name
FROM employees,departments;     #查询出2889条记录

#原因  107*27=2889
SELECT employee_id
FROM employees;   #107条记录

SELECT department_name
FROM departments;            #27条记录
```

**笛卡尔积**

![image-20220630101245898](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630101245898.png)

- 笛卡尔积的错误会在下面条件下产生：

  - 省略多个表的连接条件（或关联条件）
  - 连接条件（或关联条件）无效
  - 所有表中的所有行互相连接

- 为了避免笛卡尔积， 可以在`WHERE 加入有效的连接条件`。

加入连接条件后，查询语法：

```sql
SELECT table1.column, table2.column
FROM table1, table2
WHERE table1.column1 = table2.column2; #连接条件
```

示例

```sql
#案例：查询员工的姓名及其部门名称
SELECT last_name, department_name
FROM employees, departments
WHERE employees.department_id = departments.department_id;
```

- 如果查询语句中出现了多个表都存在的字段，则必须指明次字段都存在的表

  ```sql
  SELECT employee_id,department_name,department_id
  FROM employees,departments
  WHERE employees.department_id=departments.department_id;

  #错误代码： 1052
  #Column 'department_id' in field list is ambiguous
  # department_id不知道是哪个表中的department_id（employees，departments）


  SELECT employee_id,department_name,departments.department_id
  FROM employees,departments
  WHERE employees.department_id=departments.department_id;

  # 可以给表起别名，在SELECT和WHERE中使用表的别名
  # 如果给表起了别名，一旦在select和where中使用表名的话，则必须使用表的别名，而不能再使用表的原名
  SELECT employee_id,department_name,dept.department_id
  FROM employees emp,departments dept
  WHERE emp.`department_id`=dept.department_id;
  ```

- 从 sql 优化角度，建议多表查询时，每个字段都指明其所在的表

### 2.多表查询分类

#### 1.等值连接 VS 非等值连接

#### 2.自连接 VS 非自连接

自连接

```sql
#查询员工id,员工姓名及其管理者的id和姓名
SELECT t1.employee_id,t1.last_name,t2.employee_id,t2.last_name
FROM employees t1,employees t2
WHERE t1.manager_id=t2.employee_id;
```

![image-20220630140751561](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630140751561-16565692960781.png)

#### 3.内连接 VS 外连接

![image-20220630143825346](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630143825346.png)

```sql
#内连接：合并具有同一列的两个以上的表，结果集中不包含一个表与另一个表不匹配的行
SELECT e.last_name, e.department_id, d.department_name
FROM employees e,departments d
WHERE e.department_id = d.department_id;
```

**外连接**：合并具有同一列的两个以上的表的行，结果集中除了包含一个表与另一个表匹配的行以外

​ 还查询到了 左表 或 右表中不匹配的行

**外连接的分类**：左外连接、右外连接、满外连接

- 左外连接：交叉+左表

- 右外连接：交叉+右表

例子：查询**所有员工**的 last_name，department_name 信息

```sql
SELECT e.last_name, e.department_id, d.department_name
FROM employees e
LEFT OUTER JOIN departments d
ON (e.department_id = d.department_id);
```

![image-20220630145550026](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630145550026-16565721516422.png)

```sql
SELECT e.last_name, e.department_id, d.department_name
FROM employees e
RIGHT OUTER JOIN departments d
ON (e.department_id = d.department_id);
```

![image-20220630150743394](http://cdn.hupingsheng.com/img/MySql/selectimage-20220630150743394.png)

### 3.UNION 的使用

**合并查询结果** 利用`UNION`关键字，可以给出多条 SELECT 语句，并将它们的结果组合成单个结果集。合并 时，两个表对应的**列数和数据类型必须相同**，并且相互对应。各个 SELECT 语句之间使用 UNION 或 UNION ALL 关键字分隔。

- UNION 操作符返回两个查询的结果集的并集，去除重复记录。

- UNION ALL 操作符返回两个查询的结果集的并集。对于两个结果集的重复部分，不去重。

**举例**：查询部门编号>90 或邮箱包含 a 的员工信息

```sql
#方式1
SELECT * FROM employees WHERE email LIKE '%a%' OR department_id>90;
```

```sql
#方式2
SELECT * FROM employees WHERE email LIKE '%a%'
UNION
SELECT * FROM employees WHERE department_id>90;
```

**练习**

1. 选择所有有奖金的员工的 last_name , department_name , location_id , city

```sql
SELECT last_name,department_name,d.location_id,city
FROM employees e
LEFT OUTER JOIN departments d
ON e.`department_id`=d.`department_id`
LEFT OUTER JOIN locations l
ON d.`location_id`=l.`location_id`
WHERE commission_pct IS NOT NULL;
```

2. 查询哪些部门没有员工 ★(departments 独有的)

```sql
SELECT d.department_id
FROM departments d LEFT OUTER JOIN employees e
ON e.department_id = d.`department_id`
WHERE e.department_id IS NULL;
```

3. 查询哪个城市没有部门

```sql
SELECT l.location_id,l.city
FROM locations l LEFT JOIN departments d
ON l.`location_id` = d.`location_id`
WHERE d.`location_id` IS NULL
```

### 总结（重要）![image-20220701122638396](http://cdn.hupingsheng.com/img/MySql/selectimage-20220701122638396.png)

```sql
#中图
SELECT employee_id,department_name
FROM employees e JOIN departments d
ON e.department_id = d.department_id;

#左上
SELECT employee_id,department_name
FROM employees e LEFT JOIN departments d
ON e.department_id = d.department_id;

#右上
SELECT employee_id,department_name
FROM employees e RIGHT JOIN departments d
ON e.department_id = d.department_id;

#左中
SELECT employee_id,department_name
FROM employees e LEFT JOIN departments d
ON e.department_id = d.department_id
WHERE d.department_id IS NULL;

#右中
SELECT employee_id,department_name
FROM employees e RIGHT JOIN departments d
ON e.department_id = d.department_id
WHERE e.department_id IS NULL;

#左下
#方式1：左上图 UNOION ALL 右中
SELECT employee_id,department_name
FROM employees e LEFT JOIN departments d
ON e.department_id = d.department_id
UNION ALL
SELECT employee_id,department_name
FROM employees e RIGHT JOIN departments d
ON e.department_id = d.department_id
WHERE e.department_id IS NULL;
#方式2：左中 UNION ALL 右上

#右下
#左中+右中
SELECT employee_id,department_name
FROM employees e LEFT JOIN departments d
ON e.department_id = d.department_id
WHERE d.department_id IS NULL
UNION ALL
SELECT employee_id,department_name
FROM employees e RIGHT JOIN departments d
ON e.department_id = d.department_id
WHERE e.department_id IS NULL;
```

## 第七章

## 第八章

### 1. 聚合函数介绍

**聚合（或聚集、分组）函数**，它是对 一组数据进行汇总的函数，**输入的是一组数据的集合，输出的是单个值。**

- **什么是聚合函数**

聚合函数作用于一组数据，并对一组数据返回一个值。

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220701140229596.png" alt="image-20220701140229596" style="zoom: 50%;" />

- 聚合函数类型
  - AVG()
  - SUM()
  - MAX()
  - MIN()
  - COUNT()

#### 1.1 AVG 和 SUM 函数

```sql
#1.1  AVG/SUM：只适用于数值类型
SELECT AVG(salary),SUM(salary),AVG(salary)*107
FROM employees;
```

#### 1.2 MIN 和 MAX 函数

```sql
#1.2 MAX/MIN:适用于数值类型、字符串类型，日期类型
SELECT MAX(salary),MIN(salary)
FROM employees;

SELECT MAX(last_name)
FROM employees;
```

#### 1.3 COUNT 函数

- COUNT(\*)返回表中`记录总数`，适用于任意数据类型。

  ```sql
  #① 作用：计算指定字段在查询结构中出现的个数
  SELECT COUNT(employee_id),COUNT(salary),COUNT(salary*12)
  FROM employees;
  ```

- COUNT(expr) 返回`expr不为空`的记录总数。

  ```sql
  #② 计算指定字段的个数时，是不计算NULL值的
  SELECT COUNT(commission_pct)
  FROM employees;
  ```

- AVG 计算的只是非 NULL 记录的平均值

  ```sql
  #③ AVG=SUM/COUNT   AVG计算的只是非null着的平均值
  SELECT AVG(salary),SUM(salary)/COUNT(salary),
  AVG(commission_pct),SUM(commission_pct)/COUNT(commission_pct),
  SUM(commission_pct)/107
  FROM employees;
  ```

**问题 1：**

如果计算表中有多少条记录，怎么实现？

- 方式 1：count(\*)
- 方式 2：count(1)
- 方式 3：count(具体字段)：不一定对！（一定要非空）

**说明**：count(\*)会统计值为 NULL 的行，而 count(列名)不会统计此列为 NULL 值的行。

**问题 2：**

用 count(\*)，count(1)，count(列名)谁好呢?

- 如果是 MyISAM 引擎，则三者效率是相同的，都是 O(1)

- 如果是 InnoDB 引擎，则三者效率：COUNT(\*)=COUNT(1)>COUNT(字段)
- Innodb 引擎的表用 count(\*),count(1)直接读行数，复杂度是 O(n)，因为 innodb 真的要去数一遍。但好于具体的 count(列名)。

### 2. GROUP BY

#### 2.1 基本使用

需求：**查询各个部门的平均工资**（也是聚合函数,之前是将这个表看成一组，现在是将各个部门看成一组）

```sql
SELECT department_id,AVG(salary)
FROM employees
GROUP BY department_id           #按照部门id分组
```

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220701174221830.png" alt="image-20220701174221830" style="zoom:50%;" />

#### 2.2 使用多个列分组

**需求**：查找各个 department_id、job_id 的平均工资

```sql
SELECT department_id,job_id,AVG(salary)
FROM employees
GROUP BY department_id,job_id;
```

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220701174508464.png" alt="image-20220701174508464" style="zoom:50%;" />

**注意**

```sql
#错误的！
SELECT department_id,job_id,AVG(salary)
FROM employees
GROUP BY department_id;    #一条departmen_id对应多条job_id，无法显示
```

**结论 1**：SELECT 中出现的**非组函数**的字段，一定要出现在 GROUP BY 中

​ 反之，GROUP BY 中声明的字段可以不出现在 SELECT 中（只是可读性差点）

**结论 2**：GROUP BY 声明在 FROM 后面、WHERE 后面，ORDER BY 前面、LIMIT 前面

### 3. HAVING

#### 3.1 基本使用

**作用**：也是来过滤数据的

**需求**：查询各个部门中最高工资比 10000 高的部门信息

- 要求 1：如果过滤条件中使用了聚合函数，则必须使用 Having 来替换 WHERE。否则，报错
- 要求 2：HAVING 必须声明在`GROUP BY`的后面
- 要求 3：开发中，我们使用`HAVING`的前提是 SQL 中使用了`GROUP BY`

```sql
SELECT department_id,MAX(salary)
FROM employees
GROUP BY department_id
HAVING MAX(salary)>10000
```

**需求**：查询 10,20,30,40 中最高工资比 10000 高的部门信息

```sql
#  方式1：推荐，执行效率高于方式2
SELECT department_id,MAX(salary)
FROM employees
WHERE department_id IN(10,20,30,40)
GROUP BY department_id
HAVING  MAX(salary)>10000

#  方式2：
SELECT department_id,MAX(salary)
FROM employees
GROUP BY department_id
HAVING department_id IN(10,20,30,40) && MAX(salary)>10000
```

说明：当过滤条件中没有聚合函数时，则此过滤条件声明在 WHERE 和 HAVING 中都可以，但是，建议大家声明在 WHERE 中

#### 3.2 WHERE 和 HAVING 的对比

|        | 优点                         | 缺点                                   |
| ------ | ---------------------------- | -------------------------------------- |
| WHERE  | 先筛选数据再关联，执行效率高 | 不能使用分组中的计算函数进行筛选       |
| HAVING | 可以使用分组中的计算函数     | 在最后的结果集中进行筛选，执行效率较低 |

### 4. SELECT 的执行过程

#### 4.1 查询的结构

1. **关键字的顺序是不能颠倒的：**

```sql
SELECT ...,....,...
FROM ... (LEFT/RIGHT)JOIN ...
ON 多表的连接条件
JOIN ...
ON ...
WHERE 不包含组函数的过滤条件
AND/OR 不包含组函数的过滤条件
GROUP BY ...,...
HAVING 包含组函数的过滤条件
ORDER BY ... ASC/DESC
LIMIT ...,...

#其中：
#（1）from：从哪些表中筛选
#（2）on：关联多表查询时，去除笛卡尔积
#（3）where：从表中筛选的条件
#（4）group by：分组依据
#（5）having：在统计结果中再次筛选
#（6）order by：排序
#（7）limit：分页

#说明：在SELECT中，除了GROUP BY和LIMIT,其他位置都可以声明子查询
```

#### 4.2 SELECT 执行顺序

![image-20220701191958106](http://cdn.hupingsheng.com/img/MySql/selectimage-20220701191958106.png)

```sql
SELECT DISTINCT player_id, player_name, count(*) as num # 顺序 5

FROM player JOIN team ON player.team_id = team.team_id # 顺序 1
WHERE height > 1.80 # 顺序 2
GROUP BY player.team_id # 顺序 3
HAVING num > 2 # 顺序 4
ORDER BY num DESC # 顺序 6

LIMIT 2 # 顺序 7
```

## 第九章 子查询（重难点）

SQL 中子查询的使用大大增强了 SELECT 查询的能力，因为很多时候**查询需要从结果集中获取数据**，或者 需要从同一个表中先计算得出一个数据结果，然后与这个数据结果（可能是某个标量，也可能是某个集 合）进行比较。

### 1.需求分析与问题解决

#### 1.1 实际问题

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220701214133234.png" alt="image-20220701214133234" style="zoom:50%;" />

```sql
#方式一：两步走
SELECT salary
FROM employees
WHERE last_name = 'Abel';

SELECT last_name,salary
FROM employees
WHERE salary > 11000;

#方式二：自连接
SELECT e2.last_name,e2.salary
FROM employees e1,employees e2
WHERE e1.last_name = 'Abel'
AND e1.`salary` < e2.`salary`;

#方式三：子查询
SELECT last_name
FROM employees
WHERE salary>(
		SELECT salary
		FROM employees
		WHERE last_name='Abel'
		);
```

#### 1.2 子查询的基本使用

- 子查询的基本语法结构：

  <img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220701214519308.png" alt="image-20220701214519308" style="zoom: 67%;" />

- 子查询（内查询）在主查询之前一次执行完成。
- 子查询的结果被主查询（外查询）使用 。
- **注意事项**
  - 子查询要包含在括号内
  - 将子查询放在比较条件的右侧
  - 单行操作符对应单行子查询，多行操作符对应多行子查询

#### 1.3 子查询的分类

`分类方式1：`

我们按内查询的结果返回一条还是多条记录，将子查询分为`单行子查询`、`多行子查询` 。

- 单行子查询

  ![image-20220701215602334](http://cdn.hupingsheng.com/img/MySql/selectimage-20220701215602334-16566837636904.png)

- 多行子查询

  ![image-20220701215620463](http://cdn.hupingsheng.com/img/MySql/selectimage-20220701215620463.png)

`分类方式2:`

我们按==内查询是否被执行多次==，将子查询划分为`相关(或关联)子查询`和`不相关(或非关联)子查询`。

子查询从数据表中查询了数据结果，如果这个==数据结果只执行一次==，然后这个数据结果作为主查询的条 件进行执行，那么这样的子查询叫做`不相关子查询`。

同样，如果子查询需要执行多次，即采用循环的方式，先从外部查询开始，每次都传入子查询进行查 询，然后再将结果反馈给外部，这种嵌套的执行方式就称为`相关子查询`。(子查询每次查询结果不固定，和外查询相关)

### 2. 单行子查询

#### 2.1 单行比较操作符

| 操作符 | 含义                     |
| ------ | ------------------------ |
| =      | equal to                 |
| \>     | greater than             |
| \>=    | greater than or equal to |
| <      | less than                |
| <=     | less than or equal to    |
| !=     | not equal to             |

####　 2.2 代码示例

子查询编写技巧：

1. 从里往外写
2. 从外往里写

==题目 1：查询工资大于 149 号员工工资的员工的信息==

![image-20220701221850272](http://cdn.hupingsheng.com/img/MySql/selectimage-20220701221850272.png)

==题目 2：返回**job_id 与 141 号员工相同**，**salary 比 143 号员工多**的`员工姓名，job_id和工资`==

SELECT 查询数据 （员工姓名，job_id 和工资）

WHERE 过滤条件（job_id 与 141 号员工相同 AND salary 比 143 号员工多）

```sql
SELECT last_name,job_id,salary
FROM employees
WHERE job_id=(
		SELECT job_id
		FROM employees
		WHERE employee_id=141
		)
AND salary>(
		     SELECT salary
		     FROM employees
		     WHERE employee_id=143
		    );
```

==题目 3：返回公司工资最少的员工的 last_name,job_id 和 salary==

SELECT 查询数据(last_name,job_id 和 salary)

WHERE 过滤条件(公司工资最少)

```sql
SELECT last_name,job_id,salary
FROM employees
WHERE salary=(
		SELECT MIN(salary)
		   FROM employees
		);
```

==题目 4：查询与 141 号的 manager_id 和 department_id 相同的其他员工的 employee_id， manager_id，department_id==

方式 1：

```sql
SELECT employee_id,manager_id,department_id
FROM employees
WHERE manager_id = (
		SELECT manager_id
		FROM employees
		WHERE employee_id=141
		)
AND department_id=(
		SELECT department_id
		FROM employees
		WHERE employee_id=141
		)
AND employee_id !=141
```

方式 2：

```sql
SELECT employee_id, manager_id, department_id
FROM employees
WHERE (manager_id, department_id) =
				(SELECT manager_id, department_id
				 FROM employees
				 WHERE employee_id =141);
```

#### 2.3 HAVING 中的子查询

==题目 5：查询最低工资大于 50 号部门最低工资的部门 id 和其最低工资==

SELECT 查询数据 (department_id,MIN(salary))

HAVING 过滤条件（50 号部门最低工资）

```sql
SELECT department_id,MIN(salary)
FROM employees
GROUP BY department_id
HAVING MIN(salary)>
		   (SELECT MIN(salary)
		   FROM employees
		   WHERE department_id = 50)
```

#### 2.4 CASE 中的子查询

#### 2.5 子查询中的空值问题

子查询为 null,不返回任何行,也不报错

```sql
SELECT last_name, job_id
FROM employees
WHERE job_id =
		(SELECT job_id
		FROM employees
		WHERE last_name = 'Haas');
```

#### 2.5 非法使用子查询

`=`是单行操作符，那么与之匹配的子查询应该返回单行记录

```sql
SELECT employee_id, last_name
FROM employees
WHERE salary =
		(SELECT MIN(salary)
		FROM employees
		GROUP BY department_id);
#报错   Subquery returns more than 1 row
```

### 3. 多行子查询

- 也称为集合比较子查询
- 内查询返回多行
- 使用多行比较操作符

#### 3.1 多行比较操作符

| 操作符 | 含义                                                       |
| ------ | ---------------------------------------------------------- |
| IN     | 等于列表中的`任意一个`                                     |
| ANY    | 需要和单行比较操作符一起使用，和子查询返回的`某一个`值比较 |
| ALL    | 需要和单行比较操作符一起使用，和子查询返回的`所有`值比较   |
| SOME   | 实际上是 ANY 的别名，作用相同，一般常使用 ANY              |

#### 3.2 示例代码

==题目 1：返回其它 job_id 中比 job_id 为‘IT_PROG’部门任一工资低的员工的员工号、姓名、job_id 以及 salary==

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220702100246876.png" alt="image-20220702100246876" style="zoom:80%;" />

==题目 2：返回其它 job_id 中比 job_id 为‘IT_PROG’部门所有工资都低的员工的员工号、姓名、job_id 以及 salary==

![image-20220702100746778](http://cdn.hupingsheng.com/img/MySql/selectimage-20220702100746778.png)

==题目 3：查询平均工资最低的部门 id==

```sql
#方式1
SELECT department_id
FROM employees
GROUP BY department_id
HAVING AVG(salary)=
		   (SELECT MIN(avg_sal)
		   FROM
		   (SELECT AVG(salary) AS avg_sal
		    FROM employees
		    GROUP BY department_id
		    ) dept_avg_sal  #把查询结果当作一张表，需要给这个表取一个别名dept_avg_sal
		    )

#方式2：
SELECT department_id
FROM employees
GROUP BY department_id
HAVING AVG(salary) <= ALL(
			SELECT AVG(salary) AS avg_sal
		        FROM employees
		        GROUP BY department_id
			)
```

![image-20220702102029436](http://cdn.hupingsheng.com/img/MySql/selectimage-20220702102029436.png)

#### 3.3 空值问题

![image-20220702103712658](http://cdn.hupingsheng.com/img/MySql/selectimage-20220702103712658-16567294353231.png)

### 4. 相关子查询(难点)

#### 4.1 相关在子查询执行流程

如果子查询的执行依赖于外部查询，通常情况下都是因为**子查询中的表用到了外部的表**，并进行了条件 关联，因此**每执行一次外部查询，子查询都要重新计算一次**，这样的子查询就称之为`关联子查询`。 相关子查询按照一行接一行的顺序执行，主查询的每一行都执行一次子查询。

<img src="http://cdn.hupingsheng.com/img/MySql/selectimage-20220702104043333.png" alt="image-20220702104043333" style="zoom:67%;" />

#### 4.2 代码示例

==题目 1：查询员工中工资大于本部门平均工资的员工的 last_name,salary 和其 department_id==

![image-20220702113233311](http://cdn.hupingsheng.com/img/MySql/selectimage-20220702113233311.png)

==题目 2：查询员工的 id,salary,按照 department_name 排序==

```sql
SELECT employee_id,salary
FROM employees e
ORDER BY (SELECT department_name
	  FROM departments d
	  WHERE  e.department_id=d.department_id
	  )
```

==题目 3：若 employees 表中 employee_id 与 job_history 表中 employee_id 相同的数目不小于 2，输出这些相同 id 的员工的 employee_id,last_name 和其 job_id==

```sql
SELECT e.employee_id,e.last_name,e.job_id
FROM employees e
WHERE 2<=(
	SELECT COUNT(*)
	FROM job_history
	WHERE employee_id=e.employee_id
	)
```

#### 4.3 EXISTS 与 NOT EXISTS 关键字

- 关联子查询通常也会和`EXISTS`操作符一起来使用，用来检查在子查询中是否存在满足条件的行。

- **如果在子查询中不存在满足条件的行**：
  - 条件返回 FALSE
  - 继续在子查询中查找
- **如果在子查询中存在满足条件的行**：
  - 条件返回 TRUE
  - 不在子查询中继续查找
- NOT EXISTS 关键字表示如果不存在某种条件，则返回 TRUE，否则返回 FALSE。

==题目 4：查询公司管理者的 employee_id，last_name，job_id，department_id 信息==

```sql
#使用EXISET
SELECT employee_id, last_name, job_id, department_id
FROM employees e1
WHERE EXISTS ( SELECT *
			   FROM employees e2
		       WHERE e1.employee_id=e2.manager_id);

#自连接
SELECT DISTINCT e1.employee_id, e1.last_name, e1.job_id, e1.department_id
FROM employees e1 JOIN employees e2
WHERE e1.employee_id = e2.manager_id;

#子查询
```

==题目 5：查询 departments 表中，不存在于 employees 表中的部门的 department_id 和 department_name==

```sql
SELECT department_id, department_name
FROM departments d
WHERE NOT EXISTS (
		  SELECT 'X'
		  FROM employees
		  WHERE d.department_id = department_id
		  );
```

#### 4.4 相关更新

使用相关子查询依据一个表中的数据更新另一个表的数据。

==题目 6：在 employees 中增加一个 department_name 字段，数据为员工对应的部门名称==

```sql
UPDATE employees e
SET department_name = (SELECT department_name
					   FROM departments d
                       WHERE e.department_id = d.department_id);
```

#### 4.5 相关删除

使用相关子查询依据一个表中的数据删除另一个表的数据。

```sql
DELETE FROM employees e
WHERE employee_id in
					(SELECT employee_id
					 FROM emp_history
                     WHERE employee_id = e.employee_id);
```
