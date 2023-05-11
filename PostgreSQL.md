# Создаем контейнер с PostgreSQL с помощью Docker-compose

# Файл docker-compose.yaml

```yml
# Use postgres/example user/password credentials
version: '3.1'

services:

  db:
    image: postgres
    restart: always
    environment:
      POSTGRES_PASSWORD: cisco777!

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080

```
