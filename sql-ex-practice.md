+ [1](#1)
+ [2](#2)
+ [3](#3)
+ [4](#4)
+ [5](#5)
+ [6](#6)
+ [7](#7)
+ [8](#8)
+ [9](#9)
+ [10](#10)
+ [11](#11)
+ [12](#12)
+ [13](#13)
+ [14](#14)
+ [15](#15)
+ [16](#16)
+ [17](#17)
+ [18](#18)
+ [19](#19)
+ [20](#20)

## 1

https://sql-ex.ru/learn_exercises.php?LN=1

```sql
SELECT model, speed, hd FROM PC WHERE price<500
```

## 2

https://sql-ex.ru/learn_exercises.php?LN=2

```sql
SELECT maker FROM product WHERE type='Printer' GROUP BY maker
```

## 3

https://sql-ex.ru/learn_exercises.php?LN=3

```sql
SELECT model, ram, screen FROM Laptop WHERE price>1000
```

## 4

https://sql-ex.ru/learn_exercises.php?LN=4

```sql
SELECT * FROM Printer WHERE color = 'y'
```

## 5

https://sql-ex.ru/learn_exercises.php?LN=5

```sql
SELECT model, speed, hd FROM PC WHERE (cd = '12x' OR cd = '24x') AND price<600
```

## 6

https://sql-ex.ru/learn_exercises.php?LN=6

```sql
SELECT DISTINCT maker, speed  from Product INNER join Laptop ON Product.model = Laptop.model   
WHERE hd >= 10
```

## 7

https://sql-ex.ru/learn_exercises.php?LN=7

```sql
SELECT laptop.model , Laptop.price  from Laptop inner join product on Laptop.model = product.model  
WHERE product.maker= 'B' 
UNION 
SELECT pc.model , PC.price from PC inner join product on PC.model = product.model  
WHERE product.maker= 'B' 
UNION 
SELECT printer.model , printer.price from printer inner join product on printer.model = product.model  
WHERE product.maker= 'B'
```

## 8

https://sql-ex.ru/learn_exercises.php?LN=8

```sql
SELECT maker from product WHERE type='PC' and maker NOT IN  (select maker from product WHERE type = 'Laptop') GROUP BY maker
```

## 9

https://sql-ex.ru/learn_exercises.php?LN=9

```sql
SELECT maker  from PC INNER JOIN product on pc.model = product.model WHERE speed >= 450 
GROUP BY maker
```

## 10

https://sql-ex.ru/learn_exercises.php?LN=10

```sql

```

## 11

https://sql-ex.ru/learn_exercises.php?LN=11

```sql
SELECT avg (speed) from PC
```

## 12

https://sql-ex.ru/learn_exercises.php?LN=12

```sql
SELECT avg(speed) FROM laptop WHERE price > 1000
```

## 13

https://sql-ex.ru/learn_exercises.php?LN=13

```sql
SELECT avg(speed) from PC inner JOIN product on pc.model= product.model WHERE maker = 'A' GROUP BY maker
```

## 14

https://sql-ex.ru/learn_exercises.php?LN=14

```sql

```

## 15

https://sql-ex.ru/learn_exercises.php?LN=15

```sql
SELECT hd  FROM PC GROUP BY hd having count(model)>1
```

## 16

https://sql-ex.ru/learn_exercises.php?LN=16

```sql
SELECT DISTINCT B.model AS model, A.model AS model, A.speed, A.ram FROM PC AS A, PC B WHERE A.speed = B.speed AND A.ram = B.ram AND A.model < B.model
```

## 17

https://sql-ex.ru/learn_exercises.php?LN=17

```sql
SELECT distinct type,laptop.model,speed FROM laptop inner JOIN product on laptop.model= product.model  
WHERE speed < (SELECT MIN(speed) FROM PC)
```

## 18

https://sql-ex.ru/learn_exercises.php?LN=18

```sql
SELECT DISTINCT maker,price  FROM printer inner JOIN product ON printer.model= product.model WHERE price = (SELECT min(price)FROM printer WHERE color = 'y' ) AND color = 'y'
```

## 19

https://sql-ex.ru/learn_exercises.php?LN=19

```sql
SELECT maker ,avg(screen)AS Avg_screen 
FROM laptop inner JOIN product on laptop.model =  product.model GROUP BY maker
```

## 20

https://sql-ex.ru/learn_exercises.php?LN=20

```sql
SELECT maker , count(model) AS Count_Model FROM product WHERE type = 'pc' GROUP BY maker 
having count(model) >= 3
```
