---
## Front matter
lang: ru-RU
title: Именованные каналы
author: |
	ОЗЬЯС Стев Икнэль Дани\
	\
	НКНбд-02-21\
	\

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

Цель данной работы --- приобретение практических навыков работы с именованными каналами.

# Выполнение лабораторной работы

## Создание файлов

1. Изучил приведённые в тексте программы server.c и client.c. Взяв данные примеры за образец, напишите аналогичные программы, внеся следующие изменения:
   - Работает не 1 клиент, а несколько (например, два).(рис. [-@fig:001])

![Создание файлов common.h, server.c, client1.c, client2.c](image/1.png){ #fig:001 width=70% }

## Client2.c

   - common.h (рис. [-@fig:002])

![common.h](image/2.png){ #fig:002 width=70% }
   
##

   - Клиенты передают текущее время с некоторой периодичностью (например, раз в пять секунд). (рис. [-@fig:003])

![client1.c](image/3.png){ #fig:003 width=70% }

## Client2.c

   - Использовал функцию sleep() для приостановки работы клиента. (рис. [-@fig:004])

![client2.c](image/4.png){ #fig:004 width=70% }

## Server.c

   - Сервер работает не бесконечно, а прекращает работу через некоторое время (например, 30 сек). Использовал функцию clock() для определения времени работы сервера. (рис. [-@fig:005])

![server.c](image/5.png){ #fig:005 width=70% }


# Выводы

Я приобретил практических навыков работы с именованными каналами.

## {.standout}

Wer's nicht glaubt, bezahlt einen Taler
