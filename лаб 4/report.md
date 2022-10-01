---
# Front matter
title: "Лабораторная работа 4"
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
<p>ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ №4
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# **Теоретическое введение**

lsattr - отображает расширенные атрибуты файлов/директорий

chattr - изменяет расширенные атрибуты на файле/директории

# **Выполнение лабораторной работы**

1. Посмотрел расширенные атрибуты файла file1, они оказались пустыми.

![lsattr](img/1.jpg "lsattr")

2. Установил права 600 на файл.

3. Попытался изменить расширенные атрибуты файла от имени guest. В ответ получил ошибку

![try to change attribute](img/2.jpg "try to change attribute")

4. Зашёл из-под root и изменил атрибуты. Всё успешно поменялось. Атрибут a не даёт перезаписать файл, можно только дозаписать.

![changed attribute](img/3.jpg "changed attribute")

5. Проверил дозапись в файл, все работает

![add text to file](img/4.jpg "add text to file")

6. При этом перезапись файла, удаление или переименовывание файла не работает 

![change file](img/5.jpg "change file")

7. Изменить права на файл также нельзя.

![chmod 000](img/6.jpg "chmod 000")

8. Когда я убрал расширенный атрибут, то снова смог делать с файлом, всё что хотел.

9. Проверил то же самое с атрибутом i . Данный атрибут не даёт менять файл, в том числе нельзя удалять файл.

![attribute i](img/7.jpg "attribute i")

![attribute i](img/8.jpg "attribute i add")

# Вывод

Выполнив данную лабораторную работу, я ознакомился с расширенными атрибутами файлов, а именно a и i, первый позволяет дозаписывать файл, а второй не позволяет менять файл совсем.

# Список литературы

1. Кулябов, Д.С. - Лабораторная работа № 4. Дискреционное разграничение прав в Linux. Расширенные атрибуты
https://esystem.rudn.ru/pluginfile.php/1651887/mod_resource/content/3/004-lab_discret_extattr.pdf
