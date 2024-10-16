---
## Front matter
lang: ru-RU
title: Презентация к лабораторной работе №2
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
---

# Презентация к лабораторной работе №2

# Цель работы

Цель работы: получить практический навык работы в консоли с атрибутами файлов, закрепить теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

![Цель](images/aim.png)

# Выполнение работы

## Создание пользователя

![Создание пользователя](images/s1_add_user.png)

## Вход в систему под новым пользователем

![Вход в систему](images/s2_login_new_user.png)

## Просмотр инофрмации о домашней директории  

![Команды pwd и whoami](images/s3_pwd_whoami.png)


## Просмотр информации о пользователе

![Команды id и groups](images/s4_id_groups.png)

![Просмотр содержимого файла /etc/passwd](images/s5_passwd.png)

![Совместное использование команд cat и grep](images/s6_passwd_guest.png)


## Просмотр существующих директорий

![Просмотр директорий](images/s7_ls.png)

![Использование команды lsattr](images/s8_lsattr.png)

## Права доступа к созданной папке (по умолчанию и при изменении прав доступа)

![Права доспупа к созданной пользователем директрии](images/s9_dir.png)

![Изменение прав доступа комадной chmod](images/s10_chmod.png)

![Отказ в создании файла](images/s11_permission_denied.png)

## Заполнение таблиц «Установленные права и разрешённые действия» и «Минимально необходимые права для выполнения операций внутри директории»

![Действия с файлом и директорией](images/s12_check1.png)


# Вывод
## В рамках выполнения работы я получил практический навык работы в консоли с атрибутами файлов, закрепил теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

![s](images/conclusion.png)

# Финал

![Финал](images/final.png)