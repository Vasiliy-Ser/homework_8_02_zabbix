# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Падеев Василий`


---

### Задание 1

Установите Zabbix Server с веб-интерфейсом.

Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
3. Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
4. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.

Требования к результаты
1. Прикрепите в файл README.md скриншот авторизации в админке.
2. Приложите в файл README.md текст использованных команд в GitHub.

```
Используемые команды...
1. sudo apt install postgresql
2. sudo su
wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-6+ubuntu24.04_all.deb
dpkg -i zabbix-release_6.0-6+ubuntu24.04_all.deb
apt update
3. apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
4. su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
5. su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
6. zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
7. nano /etc/zabbix/zabbix_server.conf
8. systemctl restart zabbix-server zabbix-agent apache2
systemctl enable zabbix-server zabbix-agent apache2
9. systemctl status zabbix-server

текст использованных команд в GitHub
1. git clone https://github.com/Vasiliy-Ser/homework_8_02_zabbix.git
2. git add .
3. git commit -m "master, commit 1"
4. git push origin
```

`При необходимости прикрепитe сюда скриншоты
![1](https://github.com/Vasiliy-Ser/homework_8_02_zabbix/blob/4a21239ae32a2a984666e2453d44fa66c4df5cb9/img/1.1.png)

---

### Задание 2

Установите Zabbix Agent на два хоста.

Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
3. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
4. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
5. Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.

Требования к результаты
1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
4. Приложите в файл README.md текст использованных команд в GitHub


```
Поле для вставки кода...

1. wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-6+ubuntu24.04_all.deb
dpkg -i zabbix-release_6.0-6+ubuntu24.04_all.deb
apt update
2. apt install zabbix-agent
3. nano /etc/zabbix/zabbix_agentd.conf
4. cat /etc/zabbix/zabbix_agentd.conf | grep Server=
5. systemctl restart zabbix-agent.service
systemctl status zabbix-agent.service
```

`При необходимости прикрепитe сюда скриншоты
![2](https://github.com/Vasiliy-Ser/homework_8_02_zabbix/blob/4a21239ae32a2a984666e2453d44fa66c4df5cb9/img/2.1.png)
![3](https://github.com/Vasiliy-Ser/homework_8_02_zabbix/blob/4a21239ae32a2a984666e2453d44fa66c4df5cb9/img/2.2.png)
![4](https://github.com/Vasiliy-Ser/homework_8_02_zabbix/blob/4a21239ae32a2a984666e2453d44fa66c4df5cb9/img/2.3.png)  



---

### Задание 3 со звёздочкой*

Установите Zabbix Agent на Windows (компьютер) и подключите его к серверу Zabbix.

Требования к результаты
Приложите в файл README.md скриншот раздела Latest Data, где видно свободное место на диске C:

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`

```
Поле для вставки кода...
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`


