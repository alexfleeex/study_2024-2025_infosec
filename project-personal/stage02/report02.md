# **Отчет ко 2 этапу индивидуального проекта**
## **Common information**
discipline: Основы информационной безопасности  
group: НПМбд-02-21  
author: Ермолаев А.М.
---
---
## **Цель работы**

Приобретение практического навыка установки и развертывания веб-приложения DVWA в гостевую систему к Kali Linux.

## **Выполнение работы**

Перейдем в директорию /var/www/html/ и склонируем репозиторий командой

```
sudo git clone https://github.com/digininja/DVWA.git
```

![Клонирование репозитория](images/s1_cd_clone.png)

Перейдем в директорию config и скопируем содержимое файла config.inc.php.dist в файл 
config.inc.php командой

```
cp config.inc.php.dist config.inc.php
```

![Копирование содержимого файла](images/s2_copy_script.png)

Откроем файл командой

```
nano  config.inc.php
```

![Содержание файла config.inc.php](images/s3_db_config.png)

Как видим, файл содержит конфигурацию для подключения к СУБД MySQL как к СУБД по умолчанию.

По умолчанию в Kali Linux установлена данная СУБД (за это респект), поэтому нам нужно лишь запустить запустить процесс командой

```
sudo service mysql start
```

и посмотреть работу командой

```
sudo service mysql status
```

![Запуск сервиса MySQL](images/s4_mysql.png)

Теперь перейдем к созданию базы данных и пользователя в соответствии с файлом config.inc.php:

![Вход в оболочку MySQL](images/s5_db1.png)

![Создание базы данных и пользоватея](images/s6_db2.png)

![Проверка корректоности создания](images/s7_db3.png)

![Проверка корректоности создания](images/s8_db4.png)

После мы должны внести изменение в конфигурационный файл php.ini веб-сервера apache2 (который нам на радость установлен в Kali Linux по умолчанию).

Для корректной работы переменные allow_url_include и allow_url_fopen должны иметь значение On.

![Настройка apache2](images/s9_apache_setup.png)

Запустим процесс веб-сервера аналогично MySQL: 

![Запуск сервиса apache2](images/s10_apache_start.png)


Теперь перейдем по адресу http://127.0.0.1/DVWA/login.php.

В форму авторизации введем  имя пользовтеля admin и пароль password:

![Форма авторизации](images/s11_login.png)

Перейдя на страницу приложения, прокрутим ее вниз до кнопки "Create / Reset Database" и нажмем на нее, после чего авторизуемя повторно:

![Создание баз данных](images/s12_create_dbs.png)

Итак, веб-приложение DVWA развернуто.

![Развернутое приложение](images/s13_all_good.png)


## **Вывод**

В рамках выполнения работы я получил практический навык установки и развертывания веб-приложения DVWA в гостевую систему к Kali Linux.

## **Список литературы** ##
* https://github.com/digininja/DVWA?tab=readme-ov-file
* https://www.kali.org/
* https://www.youtube.com/watch?v=WkyDxNJkgQ4
* https://kali.tools/?p=1820