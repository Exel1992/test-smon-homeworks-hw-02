# Домашние задания по модулю «Система мониторинга Zabbix» - `Тихомиров Алексей`


### Задание 1
[Скрин] https://github.com/Exel1992/test-smon-homeworks-hw-02/blob/main/Autorisation.png

[Команды]
# wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
# apt update
# apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
nano /etc/zabbix/zabbix_server.conf
systemctl restart zabbix-server apache2
systemctl enable zabbix-server apache2
systemctl status zabbix_server.service


---

### Задание 2
[Hosts] https://github.com/Exel1992/test-smon-homeworks-hw-02/blob/main/Configuration.png

[logs] https://github.com/Exel1992/test-smon-homeworks-hw-02/blob/main/logs.png

[Latest_data] https://github.com/Exel1992/test-smon-homeworks-hw-02/blob/main/Latest_data.png

[Команды]
[]apt install zabbix-agent
systemctl restart zabbix-agent
systemctl enable zabbix-agent
nano /etc/zabbix/zabbix_agentd.conf
