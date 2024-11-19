Установка Mattermost
====================

Плэйбук для установки сервера NextCloud.

Требования
------------

- Almalinux 9

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Переменные
----------

- nextcloud_version: версия NextCloud.

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.

- [apache](./roles/apache/) - Установка сервиса Apache

- [php](./roles/php/) - Установка PHP

- [mariadb](./roles/mariadb/) - Установка БД MariaDB
