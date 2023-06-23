##### Задание №6.



## Создание SQL-запросов.

Специально созданный сайт для обучения SQL - запросам .

https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_in

### Customers

![Alt text](/misc/images/image1.png)
#### Берутся клиенты которые из Лондона и Парижа.



![Alt text](/misc/images/image-1.1.png)
#### Выберем из базы клиентов из Америки.


![Alt text](/misc/images/image-1.2.png)
#### Отсортируем клиентов по стране в алфавитном порядке.


### Categories

![Alt text](/misc/images/image-1.6.png)
##### Выберем из Categories и отсортируем по Description.



![Alt text](/misc/images/image-1.7.png)
##### Выберем CategoryID, description из Categories и сгрупируем по description.


![Alt text](/misc/images/image-1.8.png)
##### Выберем CategoryID, description из Categories и сгрупируем по CategoryID.


### Employees

![Alt text](/misc/images/image-1.9.png)
##### Отсортируем из Employees работников в BirthDate по дате рождения кроме 1928-01-01.


![Alt text](/misc/images/image-10.png)
##### Отсортируем из Employees работников в BirthDate по дате рождения по возрастанию.


![Alt text](/misc/images/Снимок_экрана__364_.png)
##### Отсортируем из Employees работников в BirthDate по дате рождения по убыванию.


### OrderDetails

![Alt text](/misc/images/Снимок_экрана__365_.png)
##### Отсортируем из OrderDetails количество в Quantity  по возрастанию.

![Alt text](/misc/images/Снимок_экрана__366_.png)

##### Отсортируем из OrderDetails количество в Quantity  по убыванию.

![Alt text](/misc/images/Снимок_экрана__367_.png)
##### Отсортируем из OrderDetails количество в OrderDetailID( деталей заказа) по убыванию.


### Orders

![Alt text](/image-15.png)
##### Выберите все записи из Orders таблицы, отсортируйте результат по алфавиту, сначала по столбцу ShipperID, затем по столбцу OrderID.


![Alt text](/image-16.png)
##### Отсортируем из Orders количество в CustomerID( пользователей ID) по убыванию.


![Alt text](/image-17.png)
##### Выберите все записи, в которых CustomerIDстолбец имеет значение 91.


### Products

![Alt text](/image-18.png)
##### Выбрать все записи из Products таблицы, отсортировать результат в алфавитном порядке по столбцу	Price.


![Alt text](/image-19.png)
##### Использование- MIN функцию для выбора записи с наименьшим значением столбца Price


![Alt text](/image-20.png)
##### Использование функции SQL - SUM для вычисления суммы всех Price значений столбцов в Products таблице.


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










