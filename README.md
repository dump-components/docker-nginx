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
docker build -t dumptec/nginx:base-1.25.2 -f Dockerfiles/1.25.2/base/Dockerfile ./Dockerfiles/1.25.2/base

# development
docker build -t dumptec/nginx:dev-1.25.2 -f Dockerfiles/1.25.2/dev/Dockerfile ./Dockerfiles/1.25.2/dev/

# production
docker build -t dumptec/nginx:1.25.2 -f Dockerfiles/1.25.2/prod/Dockerfile ./Dockerfiles/1.25.2/prod/

```

## Arquivos de configuração

> Os arquivos de configuração do host fica na pasta

* /etc/nginx/conf.d/

## Localhost green

> No google chrome é necessário permitir o arquivo server.pem nas autoridades de certificação raiz confiáveis
