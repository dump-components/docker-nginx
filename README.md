# Nginx

## User

> O campo user define qual usuário irá ser usado para rodar os processos
> dentro do container. O usuário dump já existe dentro do container com o uid 1000

```shell
user: "dump"
```

## Build images

```shell
# base
docker build -t dumptec/nginx:1.21.base -f Dockerfiles/base/Dockerfile.1.21.base ./Dockerfiles/base/

# development
docker build -t dumptec/nginx:1.21.dev -f Dockerfiles/dev/Dockerfile.1.21.dev ./Dockerfiles/dev/

# production
docker build -t dumptec/nginx:1.21 -f Dockerfiles/prod/Dockerfile.1.21 ./Dockerfiles/prod/

```

## Arquivos de configuração

> Os arquivos de configuração do host fica na pasta

* /opt/bitnami/nginx/conf/server_blocks/

## Localhost green

> No google chrome é necessário permitir o arquivo server.pem nas autoridades de certificação raiz confiáveis
