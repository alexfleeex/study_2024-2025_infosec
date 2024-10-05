---
## Front matter
lang: ru-RU
title: Презентация к лабораторной работе №4
author: Ермолаев А.М.
group: НПМбд-01-21

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
marp: true
backgroundColor: #16c9e0

---
<style>
img[alt~="center"] {
    display: block;
    margin: 0 auto;
}
</style>


# Презентация к лабораторной работе №5

---

# Цель работы

* Изучить механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. 
* Получить практический навык работы в консоли с дополнительными атрибутами. 
* Рассмотреть работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

---

# Выполнение работы

---

## Вход под пользователем guest

![center](images/s1_guest.png)

---

## Программа simpleid.c

![center](images/s2_program.png)

---

## Компиляция, выполнение и команда id 

![center](images/s3_gcc.png)

![center](images/s4_5_run_id.png)

---

## Программа simpleid2.c  

![center](images/s6_modif_prog.png)

---

## Компиляция и запуск программы

![center](images/s7_run.png)

---

## Изменение прав доступа и запуск программы

![center](images/s8_10_chown.png)

![center](images/s11_run_id.png)

---

## Добавление SetGID-бита

![center](images/s12_setgid.png)

---

## Программа readfile.c

![w:750 center](images/s13_readfile.png)

---

## Компиляция

![center](images/s14_compile.png)

---

## Изменение прав доступа

![center](images/s15_chown.png)

---

## Добавление SetUID-бита

![center](images/s16_17_chown.png)

---

## Чтение файлов

![w:700 center](images/s18_readfile.png)

![w:700 center](images/s19_etc_shadow.png)

---

## Sticky-бит

![center](images/s21_tmp.png)

---

## Файл file01.txt

![center](images/s22_echo.png)

---

## Предоставление прав доступа

![center](images/s23_chmod.png)

---

## Другие операции с файлом

![center](images/s24_25_26_cat_echo.png)

![center](images/s27_28_echo_cat.png)

---

## Другие операции с файлом

![center](images/s29_rm.png)

---

## Снятие Sticky-бита

![center](images/s30_31_su.png)

![center](images/s32_no_bit.png)

---

## Повторение команд

![center](images/s33_repeat.png)

---

## Возвращение Sticky-бита

![center](images/s34_finish.png)

---

# Вывод

В рамках выполнения работы я 

* Изучил механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. 
* Получил практический навык работы в консоли с дополнительными атрибутами. 
* Рассмотрел работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

![w:200 center](images/conclusion.png)

---

# Финал
![w:700 center](images/final.png)