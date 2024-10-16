# **Отчет к лабораторной работе №5**
## **Common information**
discipline: Основы информационной безопасности 
group: НПМбд-02-21  
author: Ермолаев А.М.

---
## **Цель работы**

* Изучить механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. 
* Получить практический навык работы в консоли с дополнительными атрибутами. 
* Рассмотреть работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

## **Выполнение работы**

Войдем в систему от имени пользователя guest:

![Пользователь guest](images/s1_guest.png)

Создадим программу simpleid.c:

![Программа simpleid.c](images/s2_program.png)

Скомплилируем программу и убедимся, что файл программы создан:

![Компиляция](images/s3_gcc.png)

Выполним программу simpleid и системную программу id:

![Выполнение программы](images/s4_5_run_id.png)

Усложним программу, добавив вывод действительных идентификаторов. Получившуюся программу назовем simpleid2.c:

![Программа simpleid2.c](images/s6_modif_prog.png)

Скомпилируем и запустим simpleid2.c:

![Компиляция и запуск программы](images/s7_run.png)

От имени суперпользователя выполним команды:

![Изменение прав доступа](images/s8_10_chown.png)

Запустим simpleid2 и id:

![Запуск программы](images/s11_run_id.png)

Проделаем тоже самое относительно SetGID-бита:

![Добавление SetGID-бита](images/s12_setgid.png)

Создадим программу readfile.c:

![Программа readfile.c](images/s13_readfile.png)

Cкомпилируем её:

![Компиляция](images/s14_compile.png)

Сменим владельца у файла readfile.c (или любого другого текстового файла в системе) и измените права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог:

![Изменение прав доступа](images/s15_chown.png)

Проверим, что пользователь guest не может прочитать файл readfile.c.
Сменим у программы readfile владельца и установим SetU’D-бит:

![Добавление SetUID-бита](images/s16_17_chown.png)

Проверим, может ли программа readfile прочитать файл readfile.c:

![Чтение файла readfile.c](images/s18_readfile.png)

Проверим, может ли программа readfile прочитать файл /etc/shadow:

![Чтение файла /etc/shadow](images/s19_etc_shadow.png)

Выясним, установлен ли атрибут Sticky на директории /tmp:

![Sticky-бит](images/s21_tmp.png)

От имени пользователя guest создадим файл file01.txt в директории /tmp со словом test:

![Файл file01.txt](images/s22_echo.png)

Просмотрим атрибуты у только что созданного файла и разрешим чтение и запись для категории пользователей «все остальные»:

![Предоставление прав доступа](images/s23_chmod.png)

От пользователя guest2 (не являющегося владельцем) попробуем прочитать файл /tmp/file01.txt, а также дозаписать в файл слово test2:

![Попытки дозаписи в файл](images/s24_25_26_cat_echo.png)

Также попробуем записать в файл /tmp/file01.txt
слово test3, стерев при этом всю имеющуюся в файле информацию:

![Попытка перезаписи файла](images/s27_28_echo_cat.png)

От пользователя guest2 попробуем удалить файл /tmp/file01.txt:

![Попытка удаления файла](images/s29_rm.png)

Повысим свои права до суперпользователя и выполним после этого команду, снимающую атрибут t (Sticky-бит) с директории /tmp:

![Снятие Sticky-бита с директории](images/s30_31_su.png)

От пользователя guest2 проверим, что атрибута t у директории /tmp нет:

![Проверка отсутствия Sticky-бита](images/s32_no_bit.png)

Повторим предыдущие шаги:

![Попытка действий с файлом](images/s33_repeat.png)

Повысим свои права до суперпользователя и верните атрибут t на директорию /tmp:

![Добавление Sticky-бита](images/s34_finish.png)

## **Вывод**
В рамках выполнения работы я 

* Изучил механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. 
* Получил практический навык работы в консоли с дополнительными атрибутами. 
* Рассмотрел работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

## **Список литературы**
* https://rockylinux.org/
* https://habr.com/ru/articles/469667/
* https://www.golinuxcloud.com/sticky-bit-linux/



