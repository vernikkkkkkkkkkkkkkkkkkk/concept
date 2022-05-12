## Кэш-память
кэш-память(eng: cache memory) 

## Определение
Кэш-память - это способ организации совместного функционирования двух типов запоминающих устройств, отличающихся временем доступа и стоимостью хранения данных, который позволяет уменьшить среднее время доступа к данным за счет динамического копирования в "быстрое" ЗУ наиболее часто используемой информации из "медленного" ЗУ.


## Примечание

В системах, оснащенных кэш-памятью, каждый запрос к оперативной памяти
выполняется в соответствии со следующим алгоритмом:

1. Просматривается содержимое кэш-памяти с целью определения, не находятся ли нужные данные в кэш-памяти; кэш-память не является адресуемой, поэтому поиск нужных данных осуществляется по содержимому - значению поля "адрес в оперативной памяти", взятому из запроса.

2. Если данные обнаруживаются в кэш-памяти, то они считываются из нее, и
результат передается в процессор.

3. Если нужных данных нет, то они вместе со своим адресом копируются из
оперативной памяти в кэш-память, и результат выполнения запроса
передается в [процессор](processor.md). При копировании данных может оказаться, что в
кэш-памяти нет свободного места, тогда выбираются данные, к которым в
последний период было меньше всего обращений, для вытеснения из кэш-
памяти. Если вытесняемые данные были модифицированы за время
нахождения в кэш-памяти, то они переписываются в оперативную память.
Если же эти данные не были модифицированы, то их место в кэш-памяти
объявляется свободным.

Схема функционирования кэш-памяти:

![cache memory](../images/cache%20memory.png)

## Связь с другими понятиями
[управление памятью](memory_management.md)
## Cсылка на библиографию
[tolstobrov-architecture-book](../bibliography/tolstobrov-architecture-book.md)
