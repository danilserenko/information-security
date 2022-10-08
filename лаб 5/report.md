---
# Front matter
title: "Лабораторная работа 5"
author: "Серенко Данил Сергеевич, НФИбд-01-19"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

<h1 align="center">
<p>РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ 
<p>Факультет физико-математических и естественных наук  
<p>Кафедра прикладной информатики и теории вероятностей
<p>ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ №5
<br></br>
<h2 align="right">
<p>дисциплина: Информационная безопасность
<p>Преподователь: Кулябов Дмитрий Сергеевич
<p>Студент: Серенко Данил Сергеевич
<p>Группа: НФИбд-01-19
<br></br>
<br></br>
<h1 align="center">
<p>МОСКВА
<p>2022 г.
</h1>

# **Цель работы**

Изучение механизмов изменения идентификаторов, применения SetUID и Sticky-битов.


# **Выполнение лабораторной работы**

1. Создал программу simpleid.c.

![simpleid](img/1.jpg "simpleid.c")

2. Скомпилировал и выполнил программу. Сравнил с id. Как видим, результат работы команд - одинаковый.

![compile and run](img/2.jpg "compile and run")

3. Усложнил программу, добавив вывод действительных идентификаторов. 

![simpleid2.c](img/3.jpg "simpleid2.c")

4. Скомпилировал и запустил simpleid2.c. 

![simpleid2](img/4.jpg "simpleid2")

5. От имени суперпользователя выполнил команды 

![chmod](img/5.jpg "chmod")

6. Запустил simpleid2 и id 

![simpleid2 run](img/6.jpg "simpleid2 run")

7. Создал программу readfile.c:

![readfile.c](img/7.jpg "readfile.c")

8. Сменил владельца у файла readfile.c  и изменил права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог.

![chown](img/8.jpg "chown")

9. guest не может прочитать файл readfile.c

![can`t read](img/9.jpg "can`t read")

10. Сменил у программы readfile владельца и установил SetU’D-бит

![readfile](img/10.jpg "readfile")

11. Проверил прочитать файл readfile и /etc/shadow

![readfile read](img/11.jpg "readfile read")

![/etc/shadow read](img/12.jpg "/etc/shadow read")

12. readfile удалось прочитать, а /etc/shadow - нет

13. Проверил sticky бит на категории tmp. Создал файл в tmp от guest и посмотерл атрибуты.

![sticky](img/13.jpg "sticky")

14. От guest2 попробовал выполнить различные операции

![guest2 file01](img/14.jpg "guest2 file01")

15. Не удалось выполнить только rm

16. Снял атрибут t (Sticky-бит) сдиректории /tmp

![-t](img/15.jpg "-t")

17. Повторил предыдущие шаги. 

![guest2 file01 try 2](img/16.jpg "guest2 file01 try 2")


# Вывод

Выполнив данную лабораторную работу, я получение практические навыков работы в консоли с дополнительными атрибутами. Рассмотрел работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Список литературы

1. Кулябов, Д.С. - Лабораторная работа № 5. Дискреционное разграничение прав в Linux.  Исследование влияния дополнительных атрибутов
https://esystem.rudn.ru/pluginfile.php/1651889/mod_resource/content/2/005-lab_discret_sticky.pdf
