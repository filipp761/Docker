# Docker
## Работа с Docker и Docker-compose

* Скачать дистрибутив Docker Engine можно на официальном сайте под любую ОС, здесь буду разбирать на примере Linux Ubuntu

https://docs.docker.com/engine/install/ubuntu/

### Установка Docker

* Перед установкой надо убедиться, что на вашей машине не установлено или нет остатков старых версий Docker

```shell
sudo apt-get remove docker docker-engine docker.io containerd runc
```

**1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:**
```shell
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
```

**2. Add Docker’s official GPG key:**
```shell
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

**3. Use the following command to set up the repository:**
```shell
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

**5. Update the apt package index:**
```shell
sudo apt-get update
```

**6. Install Docker Engine, containerd, and Docker Compose.:**
```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-compose
```

**7. Verify that the Docker Engine installation is successful by running the hello-world image.:**
```shell
sudo docker run hello-world
```
