Установка LAMP стека
====================

Плэйбук для установки стека LAMP.

Требования
------------

- **Almalinux:** 8|9
- **Arch**

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.

- [apache](./roles/apache/) - Установка и запуск apache сервера.

- [mariadb](./roles/mariadb/) - Установка БД MariaDB

- [php](./roles/php/) - Установка PHP
