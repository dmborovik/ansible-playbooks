LAMP Stack Deployment
====================

Этот проект предоставляет Ansible роли для развертывания и настройки LAMP-стека (Linux, Apache, MariaDB, PHP) на различных операционных системах: RHEL/CentOS, Debian/Ubuntu и Arch Linux.

Описание

--------
Этот проект включает в себя набор Ansible ролей для автоматизации установки и настройки LAMP-стека:

- **update_os:** Обновление операционной системы.
- **apache:** Установка и настройка веб-сервера Apache.
- **mariadb:** Установка и настройка СУБД MariaDB.
- **php:** Установка и настройка PHP.

Роли поддерживают следующие операционные системы:

- **Almalinux:** `8`|`9`
- **Arch**
- **CentOS Stream:** `9`|`10`

Требования
----------

- **Ansible:** Версия 2.9 или выше.
- **Целевые системы:** Поддерживаемые ОС (см. выше).
- **Доступ:** Убедитесь, что у вас есть доступ к целевым системам по SSH с правами sudo.

Роли
----

- [update_os](./roles/update_os/) - Обновляет операционную систему и устанавливает необходимые зависимости.

- [apache](./roles/apache/) - Устанавливает и настраивает веб-сервер Apache.

- [mariadb](./roles/mariadb/) - Устанавливает и настраивает MariaDB, включая создание базы данных и пользователя.

- [php](./roles/php/) - Устанавливает и настраивает PHP, включая необходимые модули.

Переменные
----------

Общие переменные

- ```php_version:``` Версия PHP (по умолчанию: ```8.1```).
- ```mysql_root_pass:``` Пароль пользователя root для MariaDB.
- ```db_name:``` Имя базы данных.
- ```db_user:``` Имя пользователя базы данных.
- ```db_user_pass:``` Пароль пользователя базы данных.

Роль ```apache```

- ```apache_service_name:``` Имя службы Apache (по умолчанию: ```httpd``` для RHEL, ```apache2``` для Debian).

Роль ```mariadb```

- ```version_MariaDB:``` Версия MariaDB (по умолчанию: ```11.5```).

Роль ```php```

- ```php_modules:``` Список дополнительных модулей PHP (например, ```php-mysql```, ```php-gd```).

Примеры
-------

Установка LAMP-стека с пользовательскими параметрами

```yaml
- hosts: webservers
  become: yes
  vars:
    php_version: 8.1
    mysql_root_pass: "securepassword"
    db_name: "myapp"
    db_user: "myuser"
    db_user_pass: "userpassword"
  roles:
    - update_os
    - apache
    - mariadb
    - php
```

Установка только Apache и PHP

```yaml
- hosts: webservers
  become: yes
  roles:
    - apache
    - php
```
