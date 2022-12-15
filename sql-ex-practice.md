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
+ [21](#21)
+ [22](#22)
+ [23](#23)
+ [26](#26)
+ [27](#27)
+ [28](#28)
+ [29](#29)
+ [30](#30)
+ [31](#31)
+ [33](#33)
+ [34](#34)
+ [35](#35)
+ [36](#36)
+ [37](#37)
+ [38](#38)
+ [39](#39)
+ [40](#40)
+ [41](#41)
+ [42](#42)
+ [43](#43)
+ [44](#44)
+ [45](#45)
+ [46](#46)
+ [47](#47)
+ [48](#48)
+ [49](#49)
+ [50](#50)
+ [51](#51)
+ [52](#52)
+ [53](#53)
+ [54](#54)
+ [55](#55)
+ [56](#56)
+ [57](#57)
+ [58](#58)
+ [59](#59)
+ [60](#60)
+ [61](#61)
+ [62](#62)
+ [63](#63)
+ [64](#64)
+ [65](#65)
+ [66](#66)
+ [67](#67)
+ [68](#68)
+ [69](#69)
+ [70](#70)
+ [71](#71)
+ [72](#72)
+ [73](#73)
+ [74](#74)
+ [75](#75)
+ [76](#76)
+ [77](#77)
+ [78](#78)
+ [79](#79)
+ [80](#80)
+ [81](#81)
+ [82](#82)
+ [83](#83)
+ [84](#84)
+ [85](#85)
+ [86](#86)
+ [87](#87)
+ [88](#88)
+ [89](#89)
+ [90](#90)
+ [91](#91)
+ [92](#92)
+ [93](#93)
+ [94](#94)
+ [95](#95)
+ [96](#96)
+ [97](#97)
+ [98](#98)
+ [99](#99)
+ [100](#100)

## 1

https://sql-ex.ru/learn_exercises.php?LN=1

```sql
SELECT model, speed, hd FROM PC 
WHERE price<500
```

## 2

https://sql-ex.ru/learn_exercises.php?LN=2

```sql
SELECT maker FROM product 
WHERE type='Printer' GROUP BY maker
```

## 3

https://sql-ex.ru/learn_exercises.php?LN=3

```sql
SELECT model, ram, screen FROM Laptop 
WHERE price>1000
```

## 4

https://sql-ex.ru/learn_exercises.php?LN=4

```sql
SELECT * FROM Printer 
WHERE color = 'y'
```

## 5

https://sql-ex.ru/learn_exercises.php?LN=5

```sql
SELECT model, speed, hd FROM PC 
WHERE (cd = '12x' OR cd = '24x') AND price<600
```

## 6

https://sql-ex.ru/learn_exercises.php?LN=6

```sql
SELECT DISTINCT maker, speed  FROM Product 
INNER join Laptop ON Product.model = Laptop.model   
WHERE hd >= 10
```

## 7

https://sql-ex.ru/learn_exercises.php?LN=7

```sql
SELECT laptop.model , Laptop.price FROM Laptop 
INNER JOIN product on Laptop.model = product.model  
WHERE product.maker= 'B' 
UNION 
SELECT pc.model , PC.price from PC 
INNER JOIN product on PC.model = product.model  
WHERE product.maker= 'B' 
UNION 
SELECT printer.model , printer.price from printer 
INNER JOIN product on printer.model = product.model  
WHERE product.maker= 'B'
```

## 8

https://sql-ex.ru/learn_exercises.php?LN=8

```sql
SELECT maker from product 
WHERE type='PC' and maker NOT IN  (select maker from product WHERE type = 'Laptop') 
GROUP BY maker
```

## 9

https://sql-ex.ru/learn_exercises.php?LN=9

```sql
SELECT maker  from PC INNER JOIN product on pc.model = product.model 
WHERE speed >= 450 
GROUP BY maker
```

## 10

https://sql-ex.ru/learn_exercises.php?LN=10

```sql
SELECT DISTINCT model, price FROM printer
WHERE price = (SELECT MAX(price) FROM printer)
```

## 11

https://sql-ex.ru/learn_exercises.php?LN=11

```sql
SELECT avg (speed) FROM PC
```

## 12

https://sql-ex.ru/learn_exercises.php?LN=12

```sql
SELECT avg(speed) FROM laptop 
WHERE price > 1000
```

## 13

https://sql-ex.ru/learn_exercises.php?LN=13

```sql
SELECT avg(speed) FROM PC 
INNER JOIN product on pc.model= product.model 
WHERE maker = 'A' GROUP BY maker
```

## 14

https://sql-ex.ru/learn_exercises.php?LN=14

```sql
SELECT s.class, s.name, c.country
FROM ships s
JOIN classes c ON s.class = c.class
WHERE c.numGuns >= 10
```

## 15

https://sql-ex.ru/learn_exercises.php?LN=15

```sql
SELECT hd FROM PC 
GROUP BY hd 
having count(model)>1
```

## 16

https://sql-ex.ru/learn_exercises.php?LN=16

```sql
SELECT DISTINCT B.model AS model, A.model AS model, A.speed, A.ram FROM PC AS A, PC B 
WHERE A.speed = B.speed AND A.ram = B.ram AND A.model < B.model
```

## 17

https://sql-ex.ru/learn_exercises.php?LN=17

```sql
SELECT distinct type,laptop.model,speed FROM laptop 
INNER JOIN product on laptop.model= product.model  
WHERE speed < (SELECT MIN(speed) FROM PC)
```

## 18

https://sql-ex.ru/learn_exercises.php?LN=18

```sql
SELECT DISTINCT maker,price FROM printer 
INNER JOIN product ON printer.model= product.model 
WHERE price = (SELECT min(price)FROM printer WHERE color = 'y' ) AND color = 'y'
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

## 21

https://sql-ex.ru/learn_exercises.php?LN=21

```sql
SELECT maker as Maker, MAX(price) as Max_price FROM product
JOIN pc on product.model = pc.model
GROUP BY maker
```

## 22

https://sql-ex.ru/learn_exercises.php?LN=22

```sql
SELECT speed as Speed, AVG(price) as Price
FROM pc WHERE speed > 600
GROUP BY speed
```

## 23

https://sql-ex.ru/learn_exercises.php?LN=21

```sql
SELECT maker as Maker, MAX(price) as Max_price FROM product
JOIN pc on product.model = pc.model
GROUP BY maker
```
## 24

https://sql-ex.ru/learn_exercises.php?LN=24

```sql
SELECT model FROM (SELECT model, price FROM pc
UNION
SELECT model, price FROM laptop
UNION
SELECT model, price FROM printer) table1
WHERE price = (SELECT MAX(price) 
FROM (SELECT price FROM pc
UNION
SELECT price FROM laptop
UNION
SELECT price FROM Printer) table2
)
```

## 25

https://sql-ex.ru/learn_exercises.php?LN=25

```sql
SELECT DISTINCT maker FROM product
WHERE model IN (SELECT model FROM pc
WHERE ram = (SELECT MIN(ram)FROM pc)
AND speed = (SELECT MAX(speed) FROM pc 
WHERE ram = (SELECT MIN(ram) FROM pc)
  )
)
AND maker IN (SELECT maker FROM product WHERE type='printer')
```

## 26

https://sql-ex.ru/learn_exercises.php?LN=26

```sql
SELECT AVG(price) AS AVG_price FROM (SELECT model, price FROM PC
UNION ALL
SELECT model, price FROM Laptop) AS price
INNER JOIN product ON price.model = product.model
WHERE maker = 'A'
```

## 27

https://sql-ex.ru/learn_exercises.php?LN=27

```sql
SELECT maker as Maker, AVG(hd) as AVG
FROM product JOIN pc ON product.model=pc.model
WHERE maker IN (SELECT maker FROM product WHERE type='printer')
GROUP BY maker
```

## 28

https://sql-ex.ru/learn_exercises.php?LN=28

```sql

```

## 29

https://sql-ex.ru/learn_exercises.php?LN=29

```sql

```

## 30

https://sql-ex.ru/learn_exercises.php?LN=30

```sql

```

## 31

https://sql-ex.ru/learn_exercises.php?LN=31

```sql
SELECT class, country
FROM classes
WHERE bore>=16
```

## 33

https://sql-ex.ru/learn_exercises.php?LN=33

```sql
SELECT ship
FROM Outcomes
WHERE battle = 'North Atlantic' AND result = 'sunk'
```

## 34

https://sql-ex.ru/learn_exercises.php?LN=34

```sql
SELECT name FROM classes, ships 
WHERE launched >=1922 AND displacement>35000 AND type='bb' AND ships.class = classes.class
```

## 35

https://sql-ex.ru/learn_exercises.php?LN=35

```sql
......
```

## 40

https://sql-ex.ru/learn_exercises.php?LN=40

```sql
SELECT maker, MAX(type) as Type
FROM product
GROUP BY maker
HAVING COUNT(DISTINCT type) = 1 AND COUNT(model) > 1
```

## 42

https://sql-ex.ru/learn_exercises.php?LN=42

```sql
SELECT ship, battle
FROM outcomes
WHERE result='sunk'
```

## 46

https://sql-ex.ru/learn_exercises.php?LN=46

```sql
SELECT DISTINCT ship, displacement, numguns FROM classes 
LEFT JOIN ships ON classes.class=ships.class 
RIGHT JOIN outcomes ON classes.class=ship OR ships.name=ship
WHERE battle='Guadalcanal'
```

## 50

https://sql-ex.ru/learn_exercises.php?LN=50

```sql
SELECT DISTINCT o.battle FROM ships s 
JOIN outcomes o ON s.name = o.ship 
WHERE s.class = 'kongo'
```

## 55

https://sql-ex.ru/learn_exercises.php?LN=55

```sql
SELECT c.class, min(s.launched) 
FROM classes c 
LEFT JOIN ships s ON c.class = s.class 
GROUP BY c.class
```

## 71

https://sql-ex.ru/learn_exercises.php?LN=71

```sql
SELECT p.maker FROM product p
LEFT JOIN pc ON pc.model = p.model
WHERE p.type = 'PC'
GROUP BY p.maker
HAVING COUNT(p.model) = COUNT(pc.model)
```


