# dockerfiles

Para construir as imagens (suponde que esteja em `archlinux`)

```bash
# docker build --no-cache -t <nome-da-imagem> .
docker build --no-cache -t arch .
```

Confira com

```bash
docker images
```

Para rodar um container baseado nessa imagem

```bash
# docker run --name <nome-do-container> -it <nome-da-imagem>
docker run --name arch_1 -it arch
```

Dessa forma você vai entrar no container, mas quando sair ele irá parar
de executar. Se quiser que ele fique rodando mesmo depois de sair, use

```bash
# Para rodar no background (-d = detached mode)
docker run --name arch_1 -it -d arch
# Para acessar o container
docker exec -it arch_1 bash
```

Confira com

```bash
docker ps -a
```

Para remover

```bash
# Container
docker rm arch_1
# Imagem
docker rmi arch
```
