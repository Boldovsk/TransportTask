# TransportTask
# **Блочные тесты**
Тест №1 (позитивный)

Описание: проверка корректной работы функции FormCost()

Функция FormCosts(string[] lines, TableCell[,] cells, int m, int n) – заполнение стоимости перевозки в матрицу со склада i в магазин j.

Входные данные функции: 

-) string[] lines – массив, содержащий данные о кол-ве поставщиков и потребителей, запасы поставщиков и потребности потребителей, а также стоимость перевозок между пунктами:

5 6

65 35 45 25 60

75 35 35 40 25 20

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

-)    TableCell[,] cells – матрица данных о транспортной задаче со следующими данными:  

- c - стоимость перевозки со склада i в магазин j
- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

На вход программы подаётся пустая матрица для заполнения стоимости перевозки.

-) int n и int m – кол-во потребителей и поставщиков (6 и 5 соответственно)

Ожидаемый результат: Функция вернёт массив TableCell[,] cells со следующими данными для ячейки .с :

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

Статус: Пройдено



Тест №2 (негативный)

Описание: проверка корректной работы функции FormCost()

Функция FormCosts(string[] lines, TableCell[,] cells, int m, int n) – заполнение стоимости перевозки в матрицу со склада i в магазин j.

Входные данные функции: 

-) string[] lines – массив, содержащий данные о кол-ве поставщиков и потребителей, запасы поставщиков и потребности потребителей, а также стоимость перевозок между пунктами:

5 6

65 35 45 25 60

75 35 35 40 25 20

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

-)    TableCell[,] cells – матрица данных о транспортной задаче со следующими данными:  

- c - стоимость перевозки со склада i в магазин j
- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

На вход программы подаётся пустая матрица для заполнения стоимости перевозки.

-) int n и int m – кол-во потребителей и поставщиков (6 и 5 соответственно)

Ожидаемый результат: Функция вернёт массив TableCell[,] cells **НЕ** со следующими данными для ячейки .с :

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

Статус: Пройдено



Тест №3 (позитивный)

Описание: проверка корректной работы функции TargetFunction()

Функция TargetFunction (TableCell[,] cells, int n, int m) – функция нахождения значения целевой функции Транспортной задачи.

Входные данные функции:

-) TableCell[,] cells – матрица данных о транспортной задаче со следующими данными:  

- c - стоимость перевозки со склада i в магазин j
- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

На вход программы подаётся матрица с данными о количестве перевозимых товаров

(.x) и стоимостью перевозок (.c) со склада i в магазин j. 

-) int n и int m – кол-во потребителей и поставщиков (6 и 5 соответственно)

Ожидаемый результат: Функция вернёт значение 1110

Статус: Пройдено

Тест №4 (негативный)

Описание: проверка корректной работы функции TargetFunction()

Функция TargetFunction (TableCell[,] cells, int n, int m) – функция нахождения значения целевой функции Транспортной задачи.

Входные данные функции:

-) TableCell[,] cells – матрица данных о транспортной задаче со следующими данными:  

- c - стоимость перевозки со склада i в магазин j
- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

На вход программы подаётся матрица с данными о количестве перевозимых товаров (.x) и стоимостью перевозок (.c) со склада i в магазин j. 

-) int n и int m – кол-во потребителей и поставщиков (6 и 5 соответственно)

Ожидаемый результат: Функция вернёт значение **НЕ** 1110

Статус: Пройдено



# **Интеграционные тесты**
Тест №1 (позитивный)

Взаимодействие подсистем: Подсистема проверки конечного результата FindPath(int row, int col, TableCell[,] cells) типа List<int> берёт рассчитываемое значение нового пути с помощью функций LookHorizontaly(List<int> path, int srow, int scol, int row, int col, TableCell[,] cells) и LookVerticaly(List<int> path, int srow, int scol, int row, int col, TableCell[,] cells) типов bool.

Начальное состояние: введены стоимости перевозок со складов в магазины, рассчитан предварительный путь (кол-во перевозимых товаров с определенных складов в определенные магазины).

Входные данные: 

-) TableCell[,] cells

- c - стоимость перевозки со склада i в магазин j

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

45 null null null null 20

30 5 null null null null

30 15 null null null null

null null 20 5 null null

null null null 35 25 null

На вход программы подаётся матрица с данными о количестве перевозимых товаров (.x) и стоимостью перевозок (.c) со склада i в магазин j.

-) int row, int col – позиция с которой начинается рассмотрение пути (0 и 5 соответственно)

Ожидаемый результат: будет составлен новый путь path = {5, 0, 12, 13, 7, 6, 0}, а также соответственно обновлены значения количество перевозимых товаров (.x) со склада i в магазин j в TableCell[,] cells



Тест №2 (негативный)

Взаимодействие подсистем: Подсистема проверки конечного результата FindPath(int row, int col, TableCell[,] cells) типа List<int> берёт рассчитываемое значение нового пути с помощью функций LookHorizontaly(List<int> path, int srow, int scol, int row, int col, TableCell[,] cells) и LookVerticaly(List<int> path, int srow, int scol, int row, int col, TableCell[,] cells) типов bool.

Начальное состояние: введены стоимости перевозок со складов в магазины, рассчитан предварительный путь (кол-во перевозимых товаров с определенных складов в определенные магазины).

Входные данные: 

-) TableCell[,] cells

- c - стоимость перевозки со склада i в магазин j

9 7 7 6 5 4

4 8 4 5 9 5

9 5 7 6 8 10

5 7 4 9 7 3

5 7 5 6 5 8

- sign - знак для лямбды
- s – оценка
- x - количество перевозимых товаров со склада i в магазин j

45 null null null null 20

30 5 null null null null

30 15 null null null null

null null 20 5 null null

null null null 35 25 null

На вход программы подаётся матрица с данными о количестве перевозимых товаров (.x) и стоимостью перевозок (.c) со склада i в магазин j.

-) int row, int col – позиция с которой начинается рассмотрение пути (0 и 5 соответственно)

Ожидаемый результат: будет составлен новый путь НЕ равный path = {5, 0, 12, 13, 7, 6, 0}


# **Аттестационные тесты**
Тест №1(позитивный)

Начальное состояние: Пользователь вводит в текстовый файл ввода значения в следующем формате: 

- кол-во потребителей, кол-во поставщиков – 1 строка файла
- запасы поставщиков – 2 строка файла
- потребности потребителей – 3 строка файла
- матрица, соответствующая стоимостям перевозок со склада i в магазин j

Действие: Расчёт матрицы оптимального пути и целевой функции (стоимости затрат на полный путь)

Тест проверяет правильность обработки входных данных

Ожидаемый результат: Вывод в файл правильных стоимости пути и оптимального по затратам маршрута

Статус: Пройдено

Тест №2 (негативный)

Начальное состояние: Пользователь ошибочно вводит в текстовый файл ввода значения в следующем формате: 

кол-во поставщиков, кол-во потребителей – 1 строка файла, пользователь перепутал местами поставщиков и потребителей.

- запасы поставщиков –– 2 строка файла
- потребности потребителей –– 3 строка файла
- матрица, соответствующая стоимостям перевозок со склада i в магазин j

Действие: Вывод ошибки переполнения размера если кол-во поставщиков и потребителей не совпадают, сигнал пользователю о некорректном вводе данных.

Тест проверяет реакцию программы на неправильный ввод входных данных

Ожидаемый результат: Вывод ошибки или неправильного результата работы программы

Статус: Пройдено

