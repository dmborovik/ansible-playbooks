Установка Joomla
====================

Плэйбук для установки Joomla.

Требования
------------

- **Almalinux:** 8|9

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Переменные
----------

- php-module: список модулей PHP, необходимых для установки
- db_user: имя пользователя БД для Joomla
- db_name: имя БД для Joomla.

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.
