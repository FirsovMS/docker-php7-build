# Docker-compose для легкой разработки php проектов.

Позволяет собрать контейнер с проектом в 3 клика!

# Что есть
* nginx-latest
* php 7.2-fpm
* mysql-8.0

# Как использовать
* Разместить проект в папке ``/www``.
* Править конфиг nginx.conf, размещенный в ``/hosts``.
* Добавить конфиг боевой php среды в ``/images/php/php.ini``.
* Добавьте свой dump_file.sql в ``mysql`` папку.
* . . . 
* PROIT!

Остается только собрать ваш контейнер с зависмостями.<br>
Вам полезно знать несколько команд:<br>
<ol>
	<li>Сборка контейнера<br><b>docker-compose up</b></li>
    <li>Обновление уже созданного контейнера<br><b>docker-compose --build -d</b></li>
    <li>Остановка всех контейнеров<br><b>docker stop $(docker ps -aq)</b></li>
</ol>

Пользуйтесь на здоровье!