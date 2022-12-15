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
+ [24](#24)
+ [25](#25)
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
SELECT COUNT(maker) as Quantity FROM 
(SELECT maker FROM product GROUP BY maker HAVING COUNT(*) = 1) this_table
```

## 29

https://sql-ex.ru/learn_exercises.php?LN=29

```sql
SELECT income_o.point, income_o.[date], inc, out FROM income_o 
LEFT JOIN outcome_o ON outcome_o.point = income_o.point
AND outcome_o.[date]=income_o.[date]
UNION
SELECT outcome_o.point, outcome_o.[date], inc, out FROM income_o 
RIGHT JOIN outcome_o ON outcome_o.point = income_o.point AND outcome_o.[date] = income_o.[date]
```

## 30

https://sql-ex.ru/learn_exercises.php?LN=30

```sql
SELECT point, [date], SUM(outs), SUM(incs) FROM
(SELECT point, [date], SUM(out) outs, null incs FROM outcome GROUP BY point, [date]
UNION
SELECT point, [date], null, SUM(inc) incs FROM income 
GROUP BY point, [date]) this_table GROUP BY point, [date]
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
SELECT model, type
FROM product
WHERE upper(model) NOT like '%[^A-Z]%'
OR model not like '%[^0-9]%'
```

## 36

https://sql-ex.ru/learn_exercises.php?LN=36

```sql
SELECT DISTINCT name as Name FROM (SELECT name FROM ships
UNION
SELECT ship FROM outcomes) t1
WHERE name IN (SELECT class FROM classes)
```

## 37

https://sql-ex.ru/learn_exercises.php?LN=37

```sql
SELECT c.class FROM Classes c
LEFT JOIN (Select class, name FROM Ships
UNION
SELECT Classes.class as class, Outcomes.ship as name FROM Outcomes
INNER JOIN Classes ON Outcomes.ship = Classes.class) as s On c.class = s.class
GROUP BY c.class
HAVING COUNT(s.name)=1
```

## 38

https://sql-ex.ru/learn_exercises.php?LN=38

```sql
SELECT DISTINCT country as COUNTRY FROM classes
WHERE type='bb' AND country IN
(SELECT country FROM classes
WHERE type = 'bc'
)
```

## 39

https://sql-ex.ru/learn_exercises.php?LN=39

```sql
SELECT DISTINCT ship FROM outcomes o1
LEFT JOIN Battles b1 ON b1.name = o1.battle
WHERE result = 'damaged'
and ship IN(SELECT ship FROM outcomes o2
LEFT JOIN Battles b2 ON b2.name = o2.battle
WHERE o2.ship=o1.ship AND b2.date > b1.date)
```

## 40

https://sql-ex.ru/learn_exercises.php?LN=40

```sql
SELECT maker, MAX(type) as Type
FROM product
GROUP BY maker
HAVING COUNT(DISTINCT type) = 1 AND COUNT(model) > 1
```

## 41

https://sql-ex.ru/learn_exercises.php?LN=41

```sql
SELECT 'speed' as m, CAST(speed as char) as a FROM pc WHERE code >= all(select code from pc)  
union  
SELECT 'model' as m, CAST(model as char) as a FROM pc WHERE code >= all(select code from pc)  
union  
SELECT 'ram' as m, CAST(ram as char) as a FROM pc WHERE code >= all(select code from pc)  
union  
SELECT 'hd' as m, CAST(hd as char) as a FROM pc WHERE code >= all(select code from pc)  
union  
SELECT 'cd' as m, CAST(cd as char) as a FROM pc WHERE code >= all(select code from pc)  
union  
SELECT 'price' as m, CAST(price as char) as a FROM pc WHERE code >= all(select code from pc) 
```

## 42

https://sql-ex.ru/learn_exercises.php?LN=42

```sql
SELECT ship, battle FROM outcomes
WHERE result='sunk'
```

## 43

https://sql-ex.ru/learn_exercises.php?LN=43

```sql
SELECT name 
FROM battles 
WHERE DATEPART(yy, date) NOT IN 
(SELECT DATEPART(yy, date)
FROM battles
INNER JOIN ships ON DATEPART(yy, date)=launched)
```

## 44

https://sql-ex.ru/learn_exercises.php?LN=44

```sql
SELECT name FROM ships where name like 'R%'   
union   
SELECT name FROM battles where name like 'R%'   
union   
SELECT ship FROM outcomes where ship like 'R%'  
```

## 45

https://sql-ex.ru/learn_exercises.php?LN=45

```sql
SELECT name FROM ships where name like 'R%'   
union   
SELECT name FROM battles where name like 'R%'   
union   
SELECT ship FROM outcomes where ship like 'R%'  
```

## 46

https://sql-ex.ru/learn_exercises.php?LN=46

```sql
SELECT DISTINCT ship, displacement, numguns FROM classes 
LEFT JOIN ships ON classes.class=ships.class 
RIGHT JOIN outcomes ON classes.class=ship OR ships.name=ship
WHERE battle='Guadalcanal'
```

## 47

https://sql-ex.ru/learn_exercises.php?LN=47

```sql

```

## 48

https://sql-ex.ru/learn_exercises.php?LN=48

```sql
SELECT class
FROM classes t1 LEFT JOIN outcomes t2 ON t1.class=t2.ship WHERE result='sunk'
UNION
SELECT class
FROM ships LEFT JOIN outcomes ON ships.name=outcomes.ship WHERE result='sunk'
```

## 49

https://sql-ex.ru/learn_exercises.php?LN=49

```sql
SELECT s.name 
FROM ships s 
INNER JOIN classes c ON s.name=c.class OR s.class = c.class WHERE c.bore = 16
UNION
SELECT o.ship FROM outcomes o JOIN classes c ON o.ship=c.class WHERE c.bore = 16
```

## 50

https://sql-ex.ru/learn_exercises.php?LN=50

```sql
SELECT DISTINCT o.battle FROM ships s 
INNER JOIN outcomes o ON s.name = o.ship 
WHERE s.class = 'kongo'
```

## 51

https://sql-ex.ru/learn_exercises.php?LN=51

```sql
SELECT NAME 
FROM (SELECT name as NAME, displacement, numguns FROM ships 
INNER JOIN classes ON ships.class = classes.class 
UNION 
SELECT ship as NAME, displacement, numguns FROM outcomes 
INNER JOIN classes ON outcomes.ship= classes.class) as d1 
INNER JOIN (SELECT displacement, max(numGuns) as numguns FROM (SELECT displacement, numguns FROM ships 
INNER JOIN classes ON ships.class = classes.class 
UNION 
SELECT displacement, numguns FROM outcomes 
INNER JOIN classes ON outcomes.ship= classes.class) as f 
GROUP BY displacement) as d2 ON d1.displacement=d2.displacement AND d1.numguns =d2.numguns
```

## 52

https://sql-ex.ru/learn_exercises.php?LN=52

```sql
SELECT s.name as NAME FROM ships s 
INNER JOIN classes c ON s.class = c.class WHERE country = 'japan' AND (numGuns >= '9' OR numGuns is null) 
AND (bore < '19' or bore is null) AND (displacement <= '65000' OR displacement is null) AND type='bb'
```

## 53

https://sql-ex.ru/learn_exercises.php?LN=53

```sql
SELECT CAST(AVG(numguns*1.0) AS NUMERIC(6,2)) AS Avg_nmg 
FROM classes 
WHERE type = 'bb'
```

## 54

https://sql-ex.ru/learn_exercises.php?LN=54

```sql
SELECT CAST(AVG(numguns*1.0) AS NUMERIC(6,2)) as AVG_nmg FROM (SELECT ship, numguns, type FROM Outcomes 
JOIN classes ON ship = class
UNION
SELECT name, numguns, type 
FROM ships s 
JOIN classes c ON c.class = s.class) as x 
WHERE type = 'bb'
```

## 55

https://sql-ex.ru/learn_exercises.php?LN=55

```sql
SELECT c.class, min(s.launched) 
FROM classes c 
LEFT JOIN ships s ON c.class = s.class 
GROUP BY c.class
```

## 56

https://sql-ex.ru/learn_exercises.php?LN=56

```sql
SELECT c.class, COUNT(s.ship) FROM classes c
LEFT JOIN (SELECT o.ship, sh.class FROM outcomes o
LEFT JOIN ships sh ON sh.name = o.ship
WHERE o.result = 'sunk') AS s ON s.class = c.class OR s.ship = c.class
GROUP BY c.class
```

## 57

https://sql-ex.ru/learn_exercises.php?LN=57

```sql
SELECT class, COUNT(ship) count_sunked FROM (SELECT name, class FROM ships
UNION
SELECT ship, ship FROM outcomes) t
LEFT JOIN outcomes ON name = ship AND result = 'sunk'
GROUP BY class
HAVING COUNT(ship) > 0 AND COUNT(*) > 2;
```

## 58

https://sql-ex.ru/learn_exercises.php?LN=58

```sql
SELECT m, t,
CAST(100.0*cc/cc1 AS NUMERIC(5,2)) FROM (SELECT m, t, sum(c) cc from
(SELECT DISTINCT maker m, 'PC' t, 0 c FROM product
UNION ALL
SELECT DISTINCT maker, 'Laptop', 0 FROM product
UNION ALL
SELECT DISTINCT maker, 'Printer', 0 FROM product
UNION ALL
SELECT maker, type, count(*) FROM product
GROUP BY maker, type) as tt
GROUP BY m, t) tt1
JOIN (SELECT maker, count(*) cc1 FROM product GROUP BY maker
) tt2
```

## 59

https://sql-ex.ru/learn_exercises.php?LN=59

```sql
SELECT c1, c2-
(CASE WHEN o2 is null THEN 0 ELSE o2 END)
FROM (SELECT point c1, sum(inc) c2 FROM income_o
GROUP BY point) as t1
LEFT JOIN (SELECT point o1, sum(out) o2 FROM outcome_o
GROUP BY point) as t2 ON c1=o1
```

## 60

https://sql-ex.ru/learn_exercises.php?LN=60

```sql
SELECT a.point,  case WHEN o is null  then i else i-o end remain FROM (SELECT point, sum(inc) as i 
FROM Income_o WHERE '20010415' > date group by point) as A 
LEFT JOIN (select point, sum(out) as o 
FROM Outcome_o  where '20010415' > date group by point) as B on A.point=B.point 
```

## 61

https://sql-ex.ru/learn_exercises.php?LN=61

```sql
select (select sum(inc) from income_o) - (select sum(out) from outcome_o) as remain  
```

## 62

https://sql-ex.ru/learn_exercises.php?LN=62

```sql
select  (select sum(inc) from income_o where '20010415' > date)   -  (select sum(out) from outcome_o where '20010415' > date)  as remain 
```

## 63

https://sql-ex.ru/learn_exercises.php?LN=63

```sql
SELECT name FROM Passenger
WHERE ID_psg in
(SELECT ID_psg FROM Pass_in_trip
GROUP BY place, ID_psg
HAVING count(*)>1)
```

## 64

https://sql-ex.ru/learn_exercises.php?LN=64

```sql
Select income.point, income.date, 'inc' as operation, sum(income.inc) 
from income left join outcome on income.point=outcome.point and income.date=outcome.date 
where outcome.date is null  group by income.point, income.date 
union 
Select outcome.point, outcome.date, 'out' as operation, sum(outcome.out) 
from income right join outcome on income.point=outcome.point and income.date=outcome.date 
where income.date is null group by outcome.point, outcome.date 
```

## 65

https://sql-ex.ru/learn_exercises.php?LN=65

```sql
Select row_number() over(order by maker, ans) c1, 
case when maker = lag(maker) over(order by maker) then ''
else maker end c2, type from (select distinct maker, type, case when type = 'pc' then 1 
when type = 'Laptop' then 2 when type = 'printer' then 3 end ans from product)t1 
```

## 66

https://sql-ex.ru/learn_exercises.php?LN=66

```sql
SELECT date, max(c) FROM (SELECT date,count(*) AS c FROM Trip,
(SELECT trip_no,date FROM Pass_in_trip 
WHERE date>='2003-04-01' AND date<='2003-04-07' GROUP BY trip_no, date) AS t1
WHERE Trip.trip_no=t1.trip_no AND town_from='Rostov'
GROUP BY date
UNION ALL
SELECT '2003-04-01',0
UNION ALL
SELECT '2003-04-02',0
UNION ALL
SELECT '2003-04-03',0
UNION ALL
SELECT '2003-04-04',0
UNION ALL
SELECT '2003-04-05',0
UNION ALL
SELECT '2003-04-06',0
UNION ALL
SELECT '2003-04-07',0) AS t2
GROUP BY date
```

## 67

https://sql-ex.ru/learn_exercises.php?LN=67

```sql
SELECT count(*) FROM
(SELECT TOP 1 WITH TIES count(*) c, town_from, town_to FROM trip
GROUP BY town_from, town_to
ORDER BY c desc) as t
```

## 68

https://sql-ex.ru/learn_exercises.php?LN=68

```sql
SELECT count(*) as Count FROM (SELECT TOP 1 WITH TIES sum(c) cc, c1, c2 FROM (
SELECT count(*) c, town_from c1, town_to c2 FROM trip
WHERE town_from>=town_to
GROUP BY town_from, town_to
UNION ALL
SELECT count(*) c,town_to, town_from FROM trip
WHERE town_to>town_from
GROUP BY town_from, town_to) as t
GROUP BY c1,c2
ORDER BY cc DESC
) as tt
```

## 69

https://sql-ex.ru/learn_exercises.php?LN=69

```sql
with t as (select point, "date", inc, 0 AS "out" FROM income
UNION ALL
SELECT point, "date", 0 AS inc, "out" FROM outcome
)
SELECT t.point, TO_CHAR ( t."date", 'DD/MM/YYYY') AS day,
(SELECT SUM(i.inc) FROM t i
WHERE i."date" <= t."date" and i.point = t.point )
-
(select SUM(i."out") FROM t i
WHERE i."date" <= t."date" and i.point = t.point ) AS rem FROM t
GROUP BY t.point, t."date"
```

## 70

https://sql-ex.ru/learn_exercises.php?LN=70

```sql
SELECT DISTINCT o.battle
FROM outcomes o
LEFT JOIN ships s ON s.name = o.ship
LEFT JOIN classes c ON o.ship = c.class OR s.class = c.class
WHERE c.country IS NOT NULL
GROUP BY c.country, o.battle
HAVING COUNT(o.ship) >= 3;
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

## 72

https://sql-ex.ru/learn_exercises.php?LN=72

```sql
SELECT p.maker
FROM product p
LEFT JOIN pc ON pc.model = p.model
WHERE p.type = 'PC'
GROUP BY p.maker
HAVING COUNT(p.model) = COUNT(pc.model)
```

## 73

https://sql-ex.ru/learn_exercises.php?LN=73

```sql
SELECT DISTINCT c.country, b.name FROM battles b, classes c MINUS
SELECT c.country, o.battle
FROM outcomes o
LEFT JOIN ships s ON s.name = o.ship
LEFT JOIN classes c ON o.ship = c.class OR s.class = c.class
WHERE c.country IS NOT NULL
GROUP BY c.country, o.battle
```

## 74

https://sql-ex.ru/learn_exercises.php?LN=74

```sql
SELECT c.country, c.class FROM classes c
WHERE UPPER(c.country) = 'RUSSIA' AND EXISTS (
SELECT c.country, c.class FROM classes c
WHERE UPPER(c.country) = 'RUSSIA')
UNION ALL
SELECT c.country, c.class FROM classes c
WHERE NOT EXISTS (SELECT c.country, c.class FROM classes c
WHERE UPPER(c.country) = 'RUSSIA')
```

## 75

https://sql-ex.ru/learn_exercises.php?LN=75

```sql
SELECT shipname,launched,batname FROM (SELECT s.name as shipname, launched, b.name as batname,
row_number() over (partition by s.name order by "date") as num
FROM ships s,battles b
WHERE to_char("date",'yyyy')>=launched
AND launched is not null)
WHERE num = 1
UNION
(SELECT name,launched,(SELECT name FROM battles
WHERE "date" = (SELECT MAX("date") FROM battles)) as batname FROM ships
WHERE launched is null
)
```

## 76

https://sql-ex.ru/learn_exercises.php?LN=76

```sql
SELECT shipname,launched,batname FROM (SELECT s.name as shipname, launched, b.name as batname,
row_number() over (partition by s.name order by "date") as num FROM ships s, battles b
WHERE to_char("date",'yyyy')>=launched and launched is not null)
WHERE num = 1
union
(SELECT name,launched,(select name FROM battles
WHERE "date" = (select max("date") FROM battles)) as batname FROM ships
WHERE launched is null
)
```

## 77

https://sql-ex.ru/learn_exercises.php?LN=77

```sql
SELECT TOP 1 WITH TIES * FROM (SELECT COUNT (DISTINCT P.trip_no) count, date
FROM Pass_in_trip P
INNER JOIN Trip T ON T.trip_no = P.trip_no AND town_from = 'Rostov'
GROUP BY P.trip_no, date) X
ORDER BY 1 DESC
```

## 78

https://sql-ex.ru/learn_exercises.php?LN=78

```sql
SELECT name, REPLACE(CONVERT(CHAR(12), DATEADD(m, DATEDIFF(m,0,date),0), 102),'.','-') AS first_day,
REPLACE(CONVERT(CHAR(12), DATEADD(s,-1,DATEADD(m, DATEDIFF(m,0,date)+1,0)), 102),'.','-') AS last_day
FROM Battles
```

## 79

https://sql-ex.ru/learn_exercises.php?LN=79

```sql
SELECT Passenger.name, A.minutes FROM (SELECT P.ID_psg,
SUM((DATEDIFF(minute, time_out, time_in) + 1440)%1440) AS minutes,
MAX(SUM((DATEDIFF(minute, time_out, time_in) + 1440)%1440)) OVER() AS MaxMinutes FROM Pass_in_trip P JOIN
Trip AS T ON P.trip_no = T.trip_no
GROUP BY P.ID_psg) AS A JOIN
Passenger ON Passenger.ID_psg = A.ID_psg
WHERE A.minutes = A.MaxMinutes
```

## 80

https://sql-ex.ru/learn_exercises.php?LN=80

```sql
SELECT DISTINCT maker FROM product
WHERE maker NOT IN (SELECT maker FROM product
WHERE type='PC' AND model NOT IN (
SELECT model FROM PC))
```

## 81

https://sql-ex.ru/learn_exercises.php?LN=81

```sql
SELECT O.* FROM outcome O
INNER JOIN (SELECT TOP 1 WITH TIES YEAR(date) AS Y, MONTH(date) AS M, SUM(out) AS ALL_TOTAL
FROM outcome
GROUP BY YEAR(date), MONTH(date)
ORDER BY ALL_TOTAL DESC) R ON YEAR(O.date) = R.Y AND MONTH(O.date) = R.M
```

## 82

https://sql-ex.ru/learn_exercises.php?LN=82

```sql
WITH CTE(code,price,number) AS
(SELECT PC.code,PC.price, number= ROW_NUMBER() OVER (ORDER BY PC.code) FROM PC)
SELECT CTE.code, AVG(C.price) FROM CTE
INNER JOIN CTE C ON (C.number-CTE.number)<6 AND (C.number-CTE.number)> =0
GROUP BY CTE.number,CTE.code
HAVING COUNT(CTE.number)=6
```

## 83

https://sql-ex.ru/learn_exercises.php?LN=83

```sql
SELECT name as NAME
FROM Ships AS s JOIN Classes AS cl1 ON s.class = cl1.class
WHERE
CASE WHEN numGuns = 8 THEN 1 ELSE 0 END +
CASE WHEN bore = 15 THEN 1 ELSE 0 END +
CASE WHEN displacement = 32000 THEN 1 ELSE 0 END +
CASE WHEN type = 'bb' THEN 1 ELSE 0 END +
CASE WHEN launched = 1915 THEN 1 ELSE 0 END +
CASE WHEN s.class = 'Kongo' THEN 1 ELSE 0 END +
CASE WHEN country = 'USA' THEN 1 ELSE 0 END > = 4;
```
## 84

https://sql-ex.ru/learn_exercises.php?LN=84

```sql
SELECT C.name, A.N_1_10, A.N_11_21, A.N_21_30 FROM (SELECT T.ID_comp,
SUM(CASE WHEN DAY(P.date) < 11 THEN 1 ELSE 0 END) AS N_1_10,
SUM(CASE WHEN (DAY(P.date) > 10 AND DAY(P.date) < 21) THEN 1 ELSE 0 END) AS N_11_21,
SUM(CASE WHEN DAY(P.date) > 20 THEN 1 ELSE 0 END) AS N_21_30 FROM Trip AS T 
INNER JOIN Pass_in_trip AS P ON T.trip_no = P.trip_no AND CONVERT(char(6), P.date, 112) = '200304'
GROUP BY T.ID_comp) AS A JOIN
Company AS C ON A.ID_comp = C.ID_comp
```

## 85

https://sql-ex.ru/learn_exercises.php?LN=85

```sql
SELECT maker FROM product
GROUP BY maker
HAVING count(distinct type) = 1 AND
(min(type) = 'printer' OR
(min(type) = 'pc' AND count(model) >= 3))
```

## 86

https://sql-ex.ru/learn_exercises.php?LN=86

```sql
SELECT maker, CASE count(distinct type) WHEN 2 then MIN(type) + '/' + MAX(type)
WHEN 1 then MAX(type)
WHEN 3 then 'Laptop/PC/Printer' END FROM Product
GROUP BY maker
```

## 87

https://sql-ex.ru/learn_exercises.php?LN=87

```sql
SELECT DISTINCT name, COUNT(town_to) Qty FROM Trip tr JOIN Pass_in_trip pit ON tr.trip_no = pit.trip_no 
INNER JOIN Passenger psg ON pit.ID_psg = psg.ID_psg
WHERE town_to = 'Moscow' AND pit.ID_psg NOT IN(SELECT DISTINCT ID_psg 
FROM Trip tr JOIN Pass_in_trip pit ON tr.trip_no = pit.trip_no
WHERE date+time_out = (SELECT MIN (date+time_out)
FROM Trip tr1 JOIN Pass_in_trip pit1 ON tr1.trip_no = pit1.trip_no
WHERE pit.ID_psg = pit1.ID_psg)
AND town_from = 'Moscow')
GROUP BY pit.ID_psg, name
HAVING COUNT(town_to) > 1
```

## 88

https://sql-ex.ru/learn_exercises.php?LN=88

```sql
SELECT (SELECT name FROM Passenger WHERE ID_psg = B.ID_psg) AS name, B.trip_Qty,
(SELECT name FROM Company WHERE ID_comp = B.ID_comp) AS Company
FROM (SELECT P.ID_psg, MIN(T.ID_comp) AS ID_comp, COUNT(*) AS trip_Qty, MAX(COUNT(*)) OVER() AS Max_Qty
FROM Pass_in_trip AS P 
INNER JOIN Trip AS T ON P.trip_no = T.trip_no
GROUP BY P.ID_psg
HAVING MIN(T.ID_comp) = MAX(T.ID_comp)
) 
AS B
WHERE B.trip_Qty = B.Max_Qty
```

## 89

https://sql-ex.ru/learn_exercises.php?LN=89

```sql
SELECT Maker , count(distinct model) Qty FROM Product
GROUP BY maker
HAVING count(distinct model) > = ALL
(SELECT count(distinct model) FROM Product
GROUP BY maker)
or
count(distinct model) <= ALL
(SELECT count(distinct model) FROM Product
GROUP BY maker)
```

## 90

https://sql-ex.ru/learn_exercises.php?LN=90

```sql
SELECT t1.maker, t1.model, t1.type FROM(SELECT
row_number() over (order by model) p1,
row_number() over (order by model DESC) p2,
* FROM product) t1
WHERE p1 > 3 AND p2 > 3
```

## 91

https://sql-ex.ru/learn_exercises.php?LN=91

```sql
SELECT count(maker) FROM product
WHERE maker in
(SELECT maker FROM product
GROUP BY maker
HAVING count(model) = 1
)
```

## 92

https://sql-ex.ru/learn_exercises.php?LN=92

```sql
SELECT Q_NAME FROM utQ
WHERE Q_ID IN (SELECT DISTINCT B.B_Q_ID
FROM (SELECT B_Q_ID FROM utB
GROUP BY B_Q_ID
HAVING SUM(B_VOL) = 765) AS B
WHERE B.B_Q_ID NOT IN (SELECT B_Q_ID FROM utB
WHERE B_V_ID IN (SELECT B_V_ID FROM utB
GROUP BY B_V_ID
HAVING SUM(B_VOL) < 255)))
```

## 93

https://sql-ex.ru/learn_exercises.php?LN=93

```sql

```

## 94

https://sql-ex.ru/learn_exercises.php?LN=94

```sql

```

## 95

https://sql-ex.ru/learn_exercises.php?LN=95

```sql
SELECT name,
COUNT(DISTINCT CONVERT(CHAR(24),date)+CONVERT(CHAR(4),Trip.trip_no)),
COUNT(DISTINCT plane),
COUNT(DISTINCT ID_psg),
COUNT(*) FROM Company,Pass_in_trip,Trip
WHERE Company.ID_comp=Trip.ID_comp and Trip.trip_no=Pass_in_trip.trip_no
GROUP BY Company.ID_comp,name
```

## 96

https://sql-ex.ru/learn_exercises.php?LN=96

```sql

```

## 97

https://sql-ex.ru/learn_exercises.php?LN=97

```sql
SELECT code, speed, ram, price, screen FROM laptop WHERE exists (
SELECT 1 x FROM (SELECT v, rank()over(order by v) rn
FROM( select cast(speed as float) sp, cast(ram as float) rm,
CAST(price as float) pr, cast(screen as float) sc)l unpivot(v for c in (sp, rm, pr, sc))u)l pivot(max(v) for rn in ([1],[2],[3],[4]))p
WHERE [1]*2 <= [2] and [2]*2 <= [3] AND [3]*2 <= [4]
)
```

## 98

https://sql-ex.ru/learn_exercises.php?LN=98

```sql

```

## 99

https://sql-ex.ru/learn_exercises.php?LN=99

```sql
SELECT point,"date" income_date,"date" + nvl (min(case when diff > cnt then cnt else null end), max(cnt)+1
) incass_date
FROM (SELECT i.point, i."date", (trunc(o."date") - trunc(i."date")) diff,
count(1) over (partition by i.point, i."date" order by o."date" rows between unbounded preceding and current row)-1 cnt FROM income_o i
INNER JOIN (select point, "date", 1 disabled FROM outcome_o
UNION
SELECT point, trunc("date"+7,'DAY'), 1 disabled FROM income_o) o
ON i.point = o.point
WHERE o."date" > = i."date")
GROUP BY point, "date"
```

## 100

https://sql-ex.ru/learn_exercises.php?LN=100

```sql
SELECT DISTINCT A.date , A.R, B.point, B.inc, C.point, C.out
FROM (Select distinct date, ROW_Number() OVER(PARTITION BY date ORDER BY code asc) as R FROM Income
UNION
SELECT DISTINCT date, ROW_Number() OVER(PARTITION BY date ORDER BY code asc) FROM Outcome) A
LEFT JOIN (Select date, point, inc, 
ROW_Number() OVER(PARTITION BY date ORDER BY code asc) as RI FROM Income)
B ON B.date=A.date and B.RI=A.R
LEFT JOIN (Select date, point, out,
ROW_Number() OVER(PARTITION BY date ORDER BY code asc) as RO FROM Outcome)
C ON C.date=A.date AND C.RO=A.R;
```

