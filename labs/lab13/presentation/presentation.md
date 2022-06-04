---
## Front matter
lang: ru-RU
title: Средства, применяемые при разработке программного обеспечения в ОС типа UNIX/Linux
author: |
	ОЗЬЯС Стев Икнэль Дани\
	\
	НКНбд-02-21\

institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
	\

date: 3 June, 2022 Moscow, Russia

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Цель работы

Цель данной работы --- приобрести простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования С калькулятора с простейшими функциями.

# Ход работы

1. В домашнем каталоге создал подкаталог ~/work/os/lab_prog. (рис. [-@fig:001])

![Создание подкаталога ~/work/os/lab_prog](image/1.png){ #fig:001 width=70% }

##

2. Создал в нём файлы: calculate.h, calculate.c, main.c. (рис. [-@fig:002])

![Создание файлов calculate.h, calculate.c, main.c](image/2.png){ #fig:002 width=70% }

##

   - calculate.h, (рис. [-@fig:003])

![calculate.h](image/3.png){ #fig:003 width=70% }

##

   - calculate.c, (рис. [-@fig:004])

![calculate.c](image/4.png){ #fig:004 width=70% }

##

   - main.c (рис. [-@fig:005]

![main.c](image/5.png){ #fig:005 width=70% }

##

3. Выполнил компиляцию программы посредством gcc (рис. [-@fig:006])

![Выполнение компиляции программы посредством gcc](image/6.png){ #fig:006 width=70% }

##

4. Я исправил незначительную синтаксическую ошибку.

##

5. Создал Makefile с заданным содержанием
   - CC = gcc замена слова gcc на CC
   - LIBS = -lm дополнительные опции
   - calcul: calculate.o main.o
     - gcc calculate.o main.o -o calcul $(LIBS)
     - Это команда для создания исполдняемого файла calcul

##

   - calculate.o: calculate.c calculate.h
     - gcc -c calculate.c $(CFLAGS)
     - Это команда для создания объектного файла calculate.o (рис. [-@fig:007])
   - main.o: main.c calculate.h
     - gcc -c main.c $(CFLAGS)
     - Это команда для создания объектного файла main.o

##

   - clean:
     - -rm calcul *.o *~
     - Это команда для удаления всех объектных файлов и  файлов с знаком ~ в конец

![Создание Makefile](image/7.png){ #fig:007 width=70% }

##

6. С помощью gdb выполнил отладку программы calcul (перед использованием gdb исправил Makefile)(рис. [-@fig:008]

![Выполнение отладки программы calcul](image/8.png){ #fig:008 width=70% }

##

   - Запустил отладчик GDB, загрузив в него программу для отладки:(рис. [-@fig:009]

![Запуск отладчика GDB](image/9.png){ #fig:009 width=70% }

##

   - Запустил программу внутри отладчика (рис. [-@fig:010])

![Запуск программы внутри отладчика](image/10.png){ #fig:010 width=70% }

##

   - Просмотрел исходный код используя команду list (рис. [-@fig:011])

![Просмотр исходного кода](image/11.png){ #fig:011 width=70% }

##

   - Просмотрел строки с 12 по 15 основного файла (рис. [-@fig:012])

![Просмотр строк с 12 по 15 основного файла](image/12.png){ #fig:012 width=70% }

##

   - Просмотрел определённые строки не основного файла (рис. [-@fig:013])

![Просмотр определённых строк не основного файла](image/13.png){ #fig:013 width=70% }

##

   - Установил точку останова в файле calculate.c на строке номер 21: (рис. [-@fig:014])

![Установка точки останова в файле calculate.c](image/14.png){ #fig:014 width=70% }

##

   - Вывел информацию об имеющихся в проекте точка останова: (рис. [-@fig:015])

![Вывод информации о точке останова](image/15.png){ #fig:015 width=70% }

##

   - Запустил программу внутри отладчика и убедился, что программа остановился в момент прохождения точки останова: (рис. [-@fig:016])

![Запуск программы внутри отладчика при наличии точки останова](image/16.png){ #fig:016 width=70% }

##

   - backtrace (рис. [-@fig:017])

![backtrace](image/17.png){ #fig:017 width=70% }

##

   - Посмотрел, чему равно на этом этапе значение переменной Numeral (рис. [-@fig:018])

![Значение переменной Numeral на этом этапе](image/18.png){ #fig:018 width=70% }

##

   - Сравнил с результатом вывода на экран (рис. [-@fig:019])

![Сравнение с результатом вывода на экран после исползования команды display](image/19.png){ #fig:019 width=70% }

##

   - Убрал точку останова: (рис. [-@fig:020])

![Удаление точки останова](image/20.png){ #fig:020 width=70% }

##

7. С помощью утилиты splint попробуйте проанализировал коды файлов:
   - calculate.c (рис. [-@fig:021])

![Анализ кода файла calculate.c ](image/21.png){ #fig:021 width=70% }

##

   - и main.c. (рис. [-@fig:022])

![Анализ кода файла main.c](image/22.png){ #fig:022 width=70% }

##

# Выводы

   - Я приобретил простейшие навыки разработки, анализа, тестирования и отладки приложений в ОС типа UNIX/Linux на примере создания на языке программирования С калькулятора с простейшими функциями.


## {.standout}

Wer's nicht glaubt, bezahlt einen Taler
