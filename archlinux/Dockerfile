FROM archlinux

COPY mirrorlist /etc/pacman.d/mirrorlist
COPY Rprofile /root/.Rprofile

RUN echo 'ILoveCandy' >> /etc/pacman.conf
RUN pacman -Syu --noconfirm
RUN pacman -S vim nano

# Se precisar de compilacao (recomendado se for usar o R)
# RUN pacman -S base-devel --noconfirm --needed

# R e dependencias opcionais
# RUN pacman -S tk texlive-bin gcc-fortran openblas r \
#     --noconfirm --needed
