# Основные команды Docker

* **Авторизация через терминал в Docker**
```
docker login
```

* **Скачать контейнер с Docker hub**
```
docker pull имя_контейнера
```
* **Создание контейнера**
```
docker run --name nginx -d nginx
```
* **Создание контейнера**
```
docker run имя_контейнера или id_контейнера
Наверное, вам нужно запустить контейнер и «оказаться» в его шелле:
docker run -it --rm ubuntu
-i интерактивный режим
-t подключает виртуальный терминал
--rm удалит контейнер сразу, как вы из него выйдете


Вот два варианта запустить Ubuntu, чтобы контейнер остался висеть:
docker run -d ubuntu tail -f /dev/null – тут команда-пустышка, которая будет выполняться бесконечно;

docker run -t -d ubuntu – тут подключён виртуальный терминал и bash не вылетит, а останется работать.
```
### Базовые команды Docker

* `docker --version` — проверить версию Docker.
* `docker info` — системная информация.
* `docker --help` — список доступных команд.
* `docker run IMAGE` — запустить контейнер из образа.
* `docker pull IMAGE` — скачать образ из реестра.
* `docker images` — показать все образы.
* `docker ps` — список запущенных контейнеров.
* `docker ps -a` — список всех контейнеров (включая остановленные).
* `docker stop CONTAINER` — остановить контейнер.
* `docker start CONTAINER` — запустить контейнер.
* `docker restart CONTAINER` — перезапустить.
* `docker pause / unpause CONTAINER` — приостановить/возобновить.
* `docker rm CONTAINER` — удалить контейнер.
* `docker rmi IMAGE` — удалить образ.
* `docker logs CONTAINER` — показать логи контейнера.
* `docker exec -it CONTAINER COMMAND` — выполнить команду внутри контейнера.
* `docker build -t IMAGE:TAG PATH` — собрать образ из Dockerfile.
* `docker push / pull IMAGE:TAG` — отправить/скачать образ в/из реестра.
* `docker commit CONTAINER NEW_IMAGE` — создать новый образ из контейнера.
* `docker network ls` — список сетей.
* `docker volume ls` — список томов.
* `docker login / logout` — вход/выход из реестра.
* `docker run -d IMAGE` — запуск в фоне (detached).
* `docker run -p HOST:CONTAINER IMAGE` — проброс портов.
* `docker run -v HOST:CONTAINER IMAGE` — подключение тома.
* `docker stats` — статистика ресурсов контейнера.
* `docker top CONTAINER` — процессы в контейнере.
* `docker inspect CONTAINER/IMAGE` — детальная инфа.
* `docker cp CONTAINER:PATH DEST` — копирование файлов между хостом и контейнером.

### 🔹 Docker Compose

* `docker-compose up` — поднять сервисы.
* `docker-compose down` — остановить и удалить.
* `docker-compose ps` — список контейнеров.
* `docker-compose logs` — логи сервисов.

### 🔹 Система

* `docker system df` — использование диска.
* `docker system prune` — очистка остановленных контейнеров, сетей и «висящих» образов.
* `docker system prune -a` — полная очистка всего неиспользуемого.

### 🔹 Средний уровень

* `docker history IMAGE` — история образа.
* `docker exec -u USER CONTAINER CMD` — запуск от имени пользователя.
* `docker run -e KEY=VALUE IMAGE` — переменные окружения.
* `docker run --rm IMAGE` — удалить контейнер после выхода.
* `docker build --build-arg KEY=VALUE` ... — аргументы сборки.
* `docker volume create / inspect` — работа с томами.
* `docker network create / inspect` — создание и проверка сети.
* `docker save -o FILE IMAGE` — сохранить образ в файл.
* `docker load -i FILE` — загрузить образ из файла.
* `docker export CONTAINER > FILE` — экспорт файловой системы.
* `docker import FILE` — импортировать как образ.

### 🔹 Продвинутые команды

* `docker swarm init/join/leave` — работа со Swarm.
* `docker service create/scale/logs` — управление сервисами.
* `docker stack deploy/ls/rm` — управление стэками.
* `docker secret create/ls` — секреты.
* `docker plugin install/ls/enable/disable` — плагины.
* `docker buildx` — мультиплатформенные образы.
* `docker manifest` — многоархитектурные образы.
* `docker diff CONTAINER` — изменения в файловой системе контейнера.
* `docker logs -f CONTAINER` — логи в реальном времени.
