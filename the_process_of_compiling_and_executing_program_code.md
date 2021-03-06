
##  Процесс компиляции и исполнения программного кода
 процесс компиляции и исполнения программного кода(eng: the process of compiling and executing program code) 

## Описание
Для того, чтобы написать и выполнить программу, вам необходимо следующее

1) Редактор – для ввода вашей программы, блокнот может быть использован для этого

2) [Компилятор](compiler_1.md) – для преобразования вашей программы на высоком языке в машинный код

3) Линкер – для объединения различных файловых ссылок в вашей основной программе.

4) Загрузчик – для загрузки файлов с дополнительного устройства хранения, например жесткого диска, флэш-накопителя, компакт-диска, в оперативную память для выполнения. Загрузка выполняется автоматически при выполнении вашего кода.

5) Выполнение – фактическое выполнение кода, который обрабатывается вашей ОС и процессором.
## Пример
Чтобы понять процесс компиляции Java в Java. Давайте сначала взглянем на процесс компиляции и компоновки в C.

Предположим, в основном вы вызвали две функции f1 и f2. Основная функция хранится в файле a1.c.

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code.png)

Функция f1 хранится в файле a2.c

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code%7B2%7D.png)

Функция f2 хранится в файле a3.c

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code%7B3%7D.png)

Все эти файлы, то есть a1.c, a2.c и a3.c, передаются компилятору. Чьим выводом являются соответствующие объектные файлы, которые являются машинным кодом

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code%7B4%7D.png)

Следующим шагом является объединение всех этих объектных файлов в один файл .exe с помощью компоновщика. Компоновщик объединит все эти файлы вместе и создаст файл .exe.

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code%7B5%7D.png)

Во время выполнения программы программа-загрузчик загрузит файл a.exe в оперативную память для выполнения.

![jvm](../images/The%20process%20of%20compiling%20and%20executing%20program%20code%7B6%7D.png)


## Связь с другими понятиями
[виртуальная машина Java](java_virtual_machine.md)
