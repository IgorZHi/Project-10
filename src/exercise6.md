exercise6.md
# Задание №6. Создание SQL-запросов  


## База данных Shippers (грузоотправители).  
__Запрос 1.__ Запрошены данные по грузоотправителям, отсортированные в алфавитном порядке по наименованию  

```
SELECT * FROM Shippers
ORDER BY ShipperName
```
![Shippers1](Shippers1.png)

__Запрос 2.__ Запрошены данные по грузоотправителю с наименованием Speedy Express

```
SELECT * FROM Shippers
WHERE ShipperName = 'Speedy Express'
```
![Shippers2](Shippers2.png)


__Запрос 3.__ Запрошены данные по грузоотправителям с группировкой по наименованию,  за исключением поставщика с номером телефона (503) 555-9831.

```
SELECT ShipperName, count(ShipperID) FROM Shippers
WHERE NOT Phone = '(503) 555-9831'
GROUP BY ShipperName
ORDER BY count(ShipperID)
```
![Shippers3](Shippers3.png)


## База данных Suppliers (Поставщики).  
__Запрос 1.__ Запрошены данные по поставщикам, отсортированные по алфавиту по стране нахождения, далее сортировка по алфавиту по городу в стране  

```
SELECT * FROM Suppliers  
ORDER BY Country, City;
```
![Suppliers1](Suppliers1.png)    

__Запрос 2.__ Запрошены данные по поставщикам, находящимся в Канаде

```
SELECT * FROM Suppliers 
WHERE Country = 'Canada'
```
![Suppliers2](Suppliers2.png)


__Запрос 3.__ Запрошены данные по поставщикам с группировкой по стране нахождения, отсортированные по количеству поставщиков в каждой стране (фильтрация по уменьшению), за исключением Бразилии.

```
SELECT Country, count(SupplierID) FROM Suppliers
WHERE NOT Country = 'Brazil'
GROUP BY Country
ORDER BY count(SupplierID) DESC
```
![Suppliers3](Suppliers3.png)

