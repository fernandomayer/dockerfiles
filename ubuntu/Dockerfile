FROM ubuntu

COPY sources.list /etc/apt/sources.list
COPY Rprofile /root/.Rprofile

RUN apt update && apt upgrade --yes
RUN apt install vim nano --yes

# Se precisar de compilacao (recomendado se for usar o R)
RUN apt install build-essential --yes

## Seguindo http://cran-r.c3sl.ufpr.br/bin/linux/ubuntu/
# Tudo isso para adicionar o repositorio para o R mais atual

# Necessario porque o pacote tzdata que instala como dependencia em
# seguida pede configuracao interativa e trava o terminal
ENV DEBIAN_FRONTEND="noninteractive" TZ="America/Sao_Paulo"
RUN apt install --no-install-recommends software-properties-common \
    dirmngr lsb-release wget --yes

# Chave para os pacotes do R
RUN wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc

RUN add-apt-repository "deb http://cran-r.c3sl.ufpr.br/bin/linux/ubuntu/ $(lsb_release -cs)-cran40/"

# R e dependencias opcionais
RUN apt install tk tcl texlive r-base r-base-core --yes
