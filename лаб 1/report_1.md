---
# Front matter
title: "Информационная безопасность. Отчет по лабораторной работе №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
author: "Серенко Данил Сергеевич"
group: NFIbd-01-19
institute: RUDN University, Moscow, Russian Federation

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
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

# Цель работы
Целью данной работы является приобретение практических навыков
установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов [1]. 

# Выполнение лабораторной работы
Создайте новую виртуальную машину. Для этого в VirtualBox выберите
"Машина->Создать" [2].
Укажите имя виртуальной машины (ваш логин в дисплейном классе - ymgorbunova), тип
операционной системы — Linux, RedHat (@fig:1).

![Окно «Имя машины и тип ОС»](images/1.jpg){#fig:1 width=100%}

Укажите размер основной памяти виртуальной машины (@fig:2) — 2048
МБ (или большее число, кратное 1024 МБ, если позволяют технические характеристики вашего компьютера).

![Окно «Размер основной памяти»](images/2.jpg){#fig:2 width=100%}

Задайте конфигурацию жёсткого диска — загрузочный,VDI (BirtualBox Disk
Image), динамический виртуальный диск (@fig:3-@fig:5).

![Окно подключения или создания жёсткого диска на виртуальной машине](images/3.jpg){#fig:3 width=100%}

![Окно определения типа подключения виртуального жёсткого диска](images/4.jpg){#fig:4 width=100%}

![Окно определения формата виртуального жёсткого диска](images/5.jpg){#fig:5 width=100%}

Задайте размер диска — 40 ГБ (@fig:6).

![Окно определения размера виртуального динамического жёсткого диска и его расположения](images/6.jpg){#fig:6 width=100%}

Выберите в VirtualBox для Вашей виртуальной машины "Настройки -> Носители". Добавьте новый привод оптических дисков и выберите образ операционной системы, скачанный с официального сайта (@fig:7).

![Окно «Носители» виртуальной машины: подключение образа оптического диска](images/7.jpg){#fig:7 width=100%}

Запустите виртуальную машину (@fig:7-1), выберите язык интерфейса (@fig:8) и перейдите к настройкам установки операционной системы (@fig:9).

![Запуск виртуальной машины](images/40.jpg){#fig:7-1 width=100%}

![ Установка языка интерфейса ОС](images/8.jpg){#fig:8 width=100%}

![Окно настройки установки образа ОС](images/9.jpg){#fig:9 width=100%}

При необходимости скорректируйте часовой пояс, раскладку клавиатуры
(рекомендуется добавить русский язык, но в качестве языка по умолчанию
указать английский язык; задать комбинацию клавиш для переключения
между раскладками клавиатуры — например Alt + Shift ).
В разделе выбора программ укажите в качестве базового окружения
Server with GUI , а в качестве дополнения — Development Tools (@fig:10).

![Окно настройки установки: выбор программ](images/12.jpg){#fig:10 width=100%}

Отключите KDUMP (@fig:11).

![Окно настройки установки: отключение KDUMP](images/14.jpg){#fig:11 width=100%}

Место установки ОС оставьте без изменения (@fig:12).

![Окно настройки установки: место установки](images/13.jpg){#fig:12 width=100%}

Включите сетевое соединение и в качестве имени узла укажите
user.localdomain (@fig:13), где вместо user укажите имя своего пользователя в соответствии с соглашением об именовании.

![Окно настройки установки: сеть и имя узла](images/15.jpg){#fig:13 width=100%}

Установите пароль для root (@fig:14) и пользователя с правами администратора
(@fig:15).

![Установка пароля для root](images/16.jpg){#fig:14 width=100%}

![Установка пароля для пользователя с правами администратора](images/17.jpg){#fig:15 width=100%}.

После завершения установки операционной системы корректно перезапустите виртуальную машину и примите условия лицензии.

В VirtualBox оптический диск должен отключиться автоматически, но если
это не произошло, то необходимо отключить носитель информации с образом, выбрав Свойства->Носители->Rocky-версия-dvd1.iso->Удалить устройство.

Войдите в ОС под заданной вами при установке учётной записью. В меню
Устройства виртуальной машины подключите образ диска дополнений гостевой ОС (@fig:16), при необходимости введите пароль пользователя rootвашей виртуальной ОС.

![Подключение образа диска дополнений гостевой ОС](images/19.jpg){#fig:16 width=100%}

После загрузки дополнений нажмите Return или Enter и корректно перезагрузите виртуальную машину.

##Домашнее задание
Дождитесь загрузки графического окружения и откройте терминал. В окне
терминала проанализируйте последовательность загрузки системы, выполнив команду dmesg. Можно просто просмотреть вывод этой команды: dmesg | less (@fig:17).

![Последовательность загрузки ОС](images/20.jpg){#fig:17 width=100%}

Можно использовать поиск с помощью grep: dmesg | grep -i "то, что ищем".
Получите следующую информацию.
1. Версия ядра Linux (Linux version) (@fig:18).
2. Частота процессора (Detected Mhz processor) (@fig:19).
3. Модель процессора (CPU0) (@fig:20).
4. Объем доступной оперативной памяти (Memory available) (@fig:21).
5. Тип обнаруженного гипервизора (Hypervisor detected) (@fig:22).
6. Тип файловой системы корневого раздела (@fig:23).
7. Последовательность монтирования файловых систем (@fig:24).

![Версия ядра Linux](images/21.jpg){#fig:18 width=100%}

![Частота процессора](images/22.jpg){#fig:19 width=100%}

![Модель процессора](images/23.jpg){#fig:20 width=100%}

![Объем доступной оперативной памяти](images/24.jpg){#fig:21 width=100%}

![Тип обнаруженного гипервизора](images/25.jpg){#fig:22 width=100%}

![Тип файловой системы корневого раздела](images/26.jpg){#fig:23 width=100%}

![Последовательность монтирования файловых систем](images/27.jpg){#fig:24 width=100%}

# Выводы
Приобретены практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. 

# Список литературы
1. Методические материалы курса
2. Задание к лабораторной работе № 1
