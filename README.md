
# Setup Docker Laravel 10 com PHP 8.1
Panetdigital
instalar Docker no ubuntu
Aqui está uma lista de comandos básicos do Docker que podem ser úteis para trabalhar com contêineres Docker:

### Informações do Docker:

docker version: Exibe a versão do Docker instalada.
docker info: Fornece informações detalhadas sobre o ambiente do Docker.
Imagens:

docker images ou docker image ls: Lista imagens Docker disponíveis no sistema.
docker pull nome_da_imagem:tag: Baixa uma imagem específica do Docker Hub.
docker rmi nome_da_imagem: Remove uma imagem do sistema.
### Contêineres:

docker ps: Lista contêineres em execução.
docker ps -a: Lista todos os contêineres, incluindo os que não estão em execução.
docker run nome_da_imagem: Cria e inicia um contêiner a partir de uma imagem.
docker start nome_do_contêiner: Inicia um contêiner existente.
docker stop nome_do_contêiner: Para um contêiner em execução.
docker restart nome_do_contêiner: Reinicia um contêiner.
docker rm nome_do_contêiner: Remove um contêiner.
docker exec -it nome_do_contêiner comando: Executa um comando dentro de um contêiner em execução.
Logs e Informações:

docker logs nome_do_contêiner: Exibe logs de um contêiner.
docker inspect nome_do_contêiner: Fornece informações detalhadas sobre um contêiner.
### Rede:

docker network ls: Lista redes Docker.
docker network inspect nome_da_rede: Exibe detalhes sobre uma rede específica.
### Volumes:

docker volume ls: Lista volumes Docker.
docker volume create nome_do_volume: Cria um novo volume.
docker volume inspect nome_do_volume: Exibe detalhes sobre um volume específico.
### Build e Dockerfile:

docker build -t nome_da_imagem .: Constrói uma imagem a partir de um Dockerfile no diretório atual.
docker build -f Dockerfile.alternativo -t nome_da_imagem .: Constrói uma imagem usando um Dockerfile específico.
docker-compose up: Inicia os serviços definidos no arquivo docker-compose.yml.
docker-compose down: Para e remove os serviços definidos no arquivo docker-compose.yml.
### Limpeza:

docker system prune: Remove todos os contêineres, redes não utilizadas e imagens não utilizadas.
docker container prune: Remove todos os contêineres parados.
docker image prune: Remove todas as imagens não utilizadas.
Esses são apenas alguns dos comandos básicos do Docker. Para obter informações mais detalhadas e opções disponíveis, consulte a documentação oficial do Docker.
### passo a passo

```sh
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

```
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```sh
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```sh
sudo apt-get update
```
```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```sh
sudo usermod -aG docker $USER
```

```sh
docker --version
```
### reinicializar ubuntu
```sh
sudo reboot
```
```sh
docker run hello-world
```
### Message de sucess "Pull complete"

### Passo a passo
Clone Repositório
```sh
mkdir app-laravel
```
```sh
cd app-laravel
```
```sh
git clone https://github.com/panetdigital/laravel-10-docker.git
```
```sh
cd laravel-10-docker/
```
Crie o Arquivo .env
```sh
cp .env.example .env
```


Atualize as variáveis de ambiente do arquivo .env
```dosini
APP_NAME=Panet-digital
APP_URL=http://localhost:8989

DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=nome_que_desejar_db
DB_USERNAME=nome_usuario
DB_PASSWORD=senha_aqui

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```
```sh
sudo apt  install docker-compose
```
Suba os containers do projeto
```sh
docker-compose up -d
```


Acesse o container app
```sh
docker-compose exec app bash
```


Instale as dependências do projeto
```sh
composer install
```


Gere a key do projeto Laravel
```sh
php artisan key:generate
```


Acesse o projeto
[http://localhost:8989](http://localhost:8989)
