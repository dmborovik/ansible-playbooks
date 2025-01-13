Установка Wordpress
====================

Плэйбук для установки Wordpress. Используется БД - MariaDB, сервер - OpenLiteSpeed.

Требования
------------

- **AlmaLinux:** 8
- **Ubuntu:** 24

Запуск плэйбука
----------------

    ansible-playbook playbook.yaml

Переменные
----------

- ***lsphp_module:*** Модули LSPHP, необходимые для работы приложения
- ***work_dir:*** Рабочий кталог Wordpress.
- ***server_owner:*** Владелец рабочего каталога Wordpress
- ***server_group:*** Группа владельца рабочего каталога Wordpress
- ***multisite:*** Включение функции multisite (True/False)

Роли
----

- [update_os](./roles/update_os/) - Обновление системы. Внимание, это может превести к рестарту ОС. Если вам этого не требуется, закомментируйте роль.

- [openlitespeed](./roles/openlitespeed/) - Установка сервиса OpenLiteSpeed. В качестве параметра указывается порт, который устанавливается по умолчанию для Listener.

- [lsphp](./roles/lsphp/) - Установка LSPHP

- [mariadb](./roles/mariadb/) - Установка БД MariaDB
