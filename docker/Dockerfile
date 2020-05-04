FROM ubuntu:18.04
RUN apt-get update
RUN apt-get install -y qt5-default libftdi1-dev libqt5serialport5-dev
RUN apt-get install -y make build-essential
ARG USER
ARG UID
RUN useradd --create-home --shell /bin/bash --uid ${UID} ${USER}
USER ${USER}
WORKDIR /home/${USER}
CMD bash
