Установка Mattermost
====================

Плэйбук для установки сервера Mattermost.

Требования
------------

- **Almalinux:** 9

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Переменные
----------

- mattermost_version: версия mattermost.

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.

- [mariadb](./roles/mariadb/) - Установка БД MariaDB
