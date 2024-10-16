# **Отчет к лабораторной работе №6**
## **Common information**
discipline: Основы информационной безопасности 
group: НПМбд-02-21  
author: Ермолаев А.М.

---
## **Цель работы**

* Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux
* Проверить работу SELinx на практике совместно с веб-сервером Apache.

## **Выполнение работы**

Войдем в систему с полученными учётными данными и убедимся, что SELinux работает в режиме enforcing политики targeted с помощью команд ```getenforce``` и ```sestatus```.

![Команды getenforce и seastatus](images/s1_getenforce.png)

Обратим с помощью браузера к веб-серверу, запущенному на вашем компьютере, и убедимся, что последний работает (в нашем случае его надо предварительно запустить):

![Статус сервиса Apache2](images/s2_apache.png)

Найдем веб-сервер Apache в списке процессов, определим его контекст безопасности:

![Контекст безопасности Apache2](images/s3_processes.png)

Посмотрим текущее состояние переключателей SELinux для Apache:

![Текущее состояние переключателей для Apache2](images/s4_sestatus.png)

Посмотрим статистику по политике с помощью команды ```seinfo```, также определим множество пользователей, ролей, типов:

![Команда seinfo](images/s5_seinfo.png)

Определим типы файлов и поддиректорий, находящихся в директории /var/www,  /var/www/html, а также круг пользователей, которым разрешено создание файлов в
директории /var/www/html:

![Тип файлов и поддиректорий](images/s6_s8_ls.png)

Создадим от имени суперпользователя html-файл
/var/www/html/test.html:

![Файл test.html](images/s9_html.png)

Проверим контекст созданного файла:

![Контекст файла](images/s10_context.png)

Обратимся к файлу через веб-сервер, введя в браузере адрес
```http://127.0.0.1/test.html```:

![Обращение к веб-серверу](images/s11_working.png)

Изучим справку man httpd_selinux. Проверим контекст файла:

![Контекст файла](images/s12_context.png)

Изменим контекст файла /var/www/html/test.html с
httpd_sys_content_t на любой другой, к которому процесс httpd не должен иметь доступа, например, на samba_share_t:

![Изменение контекста файла](images/s13_chcon.png)

Попробуем ещё раз получить доступ к файлу через веб-сервер, введя в браузере адрес ```http://127.0.0.1/test.html```:

![Потвторное обращение к веб-серверу](images/s14_403.png)

Просмотрим log-файлы веб-сервера Apache и системный лог-файл:

![Просмотр логов](images/s15_logs.png)

Попробуем запустить веб-сервер Apache на прослушивание ТСР-порта
81 Для
этого в файле /etc/httpd/httpd.conf найдем строчку Listen 80 и
заменим её на Listen 81:

![Изменение прослушиваемого порта](images/s16_listen81.png)

Выполним перезапуск веб-сервера Apache:

![Перезапуск Apache2](images/s17_ok.png)

Проанализируем лог-файлы:

![Анализ логов](images/s18_logs.png)

Выполним команду
```
semanage port -a -t http_port_t -р tcp 81
```
После этого проверим список портов командой
```
semanage port -l | grep http_port_t
```

После чего попробуем запустить веб-сервер Apache ещё раз:

![Просмотр доступных портов](images/s19_20_semanage.png)

Вернем контекст httpd_sys_cоntent__t к файлу /var/www/html/ test.html:

![Контекст файла](images/s21_chcon_test.png)

Исправим конфигурационный файл apache, вернув Listen 80.


![Изменение конфигурационного файла  Apache2](images/s22_listen80.png)

Удалим привязку http_port_t к 81 порту. Затем удалим файл /var/www/html/test.html:

![Удаление привязки к порту и фалйа](images/s22_s24_semanage_rm.png)


## **Вывод**
В рамках выполнения работы я 

* Развил навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux
* Проверил работу SELinx на практике совместно с веб-сервером Apache.

## **Список литературы**
* https://rockylinux.org/
* https://habr.com/ru/articles/469667/
* https://www.linuxteck.com/how-to-install-apache-on-rocky-linux/
* https://habr.com/ru/companies/kingservers/articles/209644/



