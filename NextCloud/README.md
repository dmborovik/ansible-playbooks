Установка Mattermost
====================

Плэйбук для установки сервера NextCloud.

Требования
------------

- Almalinux 8|9

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Переменные
----------

- nextcloud_version: версия NextCloud.
- php_module: Модули PHP, необходимые для работы приложения

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.

- [apache](./roles/apache/) - Установка сервиса Apache

- [php](./roles/php/) - Установка PHP

- [mariadb](./roles/mariadb/) - Установка БД MariaDB
