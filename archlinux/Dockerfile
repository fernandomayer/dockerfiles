FROM archlinux

COPY mirrorlist /etc/pacman.d/mirrorlist

RUN echo 'ILoveCandy' >> /etc/pacman.conf
RUN pacman -Syu --noconfirm

# Se precisar de compilacao
# RUN pacman -S base-devel --noconfirm --needed

# R e dependencias opcionais
# RUN pacman -S tk texlive-bin gcc-fortran openblas r \
#     --noconfirm --needed
