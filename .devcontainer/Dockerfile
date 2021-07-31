FROM tkdnn:base

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y ca-certificates python3-dev sudo git zsh curl
RUN ln -sv /usr/bin/python3 /usr/bin/python

# create a non-root user
ARG USER_ID=1000
RUN useradd -m --no-log-init --system  --uid ${USER_ID} appuser -g sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER appuser
WORKDIR /home/appuser

# RUN git clone https://github.com/josht000/zsh-setup.git && cd zsh-setup && ./zsh-setup.sh

ENV DEBIAN_FRONTEND dialog

# docker run --rm -it --gpus 1 -e DISPLAY=172.26.208.1:0 -v C:\data\tkdnn:/home/appuser/tkdnn tkdnn:dev