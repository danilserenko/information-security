

#### РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ
#### Факультет физико-математических и естественных наук  
#### Кафедра прикладной информатики и теории вероятностей 
#### ПРЕЗЕНТАЦИЯ ПО ЛАБОРАТОРНОЙ РАБОТЕ №5

###### дисциплина: Информационная безопасность
###### Преподователь: Кулябов Дмитрий Сергеевич
###### Студент: Серенко Данил Сергеевич
###### Группа: НФИбд-01-19
МОСКВА
2022 г.

---

# **Прагматика выполнения лабораторной работы**

- работа с дополнительными атрибутами

---

# **Цель работы**

Изучение механизмов изменения идентификаторов, применения SetUID и Sticky-битов.

---

# **Выполнение лабораторной работы**

# 1. Создание программы simpleid.c. и выполнение
![simpleid](img/1.jpg "simpleid.c")


![compile and run](img/2.jpg "compile and run")

---

# 2. Создание программы simpleid2.c. и выполнение
![simpleid2.c](img/3.jpg "simpleid2.c")


![simpleid2](img/4.jpg "simpleid2")

---

# 3. Установка новых аттрибутов и запуск simpledid2
![chmod](img/5.jpg "chmod")


![simpleid2 run](img/6.jpg "simpleid2 run")

---

# 4. Создание программы readfile.c
![readfile.c](img/7.jpg "readfile.c")

---

# 5. Смена владельца readfile
![chown](img/8.jpg "chown")


![cant read](img/9.jpg "cant read")

---

# 6. Смена владельца readfile и установил SetU’D-бит
![readfile](img/10.jpg "readfile")


![readfile read](img/11.jpg "readfile read")


![/etc/shadow read](img/12.jpg "/etc/shadow read")

---

# 7. Проверка sticky бит на категории tmp.

![sticky](img/13.jpg "sticky")

---

# 8. Выполнение различных операций от guest2

![guest2 file01](img/14.jpg "guest2 file01")

---

# 9. Снятие атрибут t (Sticky-бит) сдиректории /tmp и выполнение предыдущих шагов

![-t](img/15.jpg "-t")


![guest2 file01 try 2](img/16.jpg "guest2 file01 try 2")

---

# Вывод

Выполнив данную лабораторную работу, я получение практические навыков работы в консоли с дополнительными атрибутами. Рассмотрел работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.