---
## Front matter
lang: ru-RU
title: Презентация к лабораторной работе №6
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


# Презентация к лабораторной работе №6

---

# Цель работы

* Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux
* Проверить работу SELinx на практике совместно с веб-сервером Apache.

![center](images/aim.png)

---

# Выполнение работы

---

## Команды getenforce и seastatus

![center](images/s1_getenforce.png)

---

## Запуск сервиса Apache2

![center](images/s2_apache.png)

---

## Контекст безопасности Apache2

![center](images/s3_processes.png)

---

## Текущее состояние переключателей для Apache2 

![center w:1000](images/s4_sestatus.png)

---

## Команда seinfo

![center](images/s5_seinfo.png)

---

## Тип файлов и поддиректорий

![center](images/s6_s8_ls.png)

---

## Файл test.html

![center](images/s9_html.png)

---

## Контекст файла

![center](images/s10_context.png)

---

## Обращение к веб-серверу

![center](images/s11_working.png)

---

## Контекст файла

![center](images/s12_context.png)

---

## Изменение контекста файла

![center](images/s13_chcon.png)

---

## Потвторное обращение к веб-серверу

![center](images/s14_403.png)

---

## Просмотр логов

![center w:1000](images/s15_logs.png)

---

## Изменение прослушиваемого порта

![center](images/s16_listen81.png)

---

## Перезапуск Apache2

![center](images/s17_ok.png)

---

## Анализ логов

![center](images/s18_logs.png)

---

## Просмотр доступных портов

![center](images/s19_20_semanage.png)

---

## Контекст файла

![center](images/s21_chcon_test.png)

---

## Изменение конфигурационного файла  Apache2

![center](images/s22_listen80.png)


---

## Удаление привязки к порту и файла

![center](images/s22_s24_semanage_rm.png)

---

# Вывод

В рамках выполнения работы я 

* Развил навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux
* Проверил работу SELinx на практике совместно с веб-сервером Apache.

![center](images/conclusion.png)

---

# Финал
![w:700 center](images/final.png)