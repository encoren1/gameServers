FROM debian:buster-slim
ARG STEAM_UID=10000

LABEL mantainer="encore.n1@gmail.com"

ENV USER_NAME steam
ENV HOME_DIR /home/steam
ENV STEAMCMD_DIR /home/steam/steamcmd

# Install dependencies
RUN set -x \
    && dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y --no-install-recommends --no-install-suggests \
      lib32stdc++6 \
      lib32gcc1 \
      libsdl2-2.0-0:i386 \
      curl \
      locales \
      ca-certificates \
    && sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen \
    && dpkg-reconfigure --frontend=noninteractive locales \
    && useradd -u ${STEAM_UID} -d /home/${USER_NAME} -m -s /bin/bash ${USER_NAME} \
    && apt-get autoclean \
  	&& apt-get autoremove -y \
  	&& rm -rf /var/lib/apt/lists/*

USER ${USER_NAME}

#Get code
RUN set -x \
    && mkdir -p ${STEAMCMD_DIR} \
    && curl -s "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar -xzvf - -C ${STEAMCMD_DIR} \
    && cd ${STEAMCMD_DIR} \
    && ./steamcmd.sh +login anonymous +quit \
    && mkdir -p ${HOME_DIR}/.steam/sdk32 \
    && ln -s ${STEAMCMD_DIR}/linux32/steamclient.so ${HOME_DIR}/.steam/sdk32/steamclient.so \
    && ln -s ${STEAMCMD_DIR}/linux32/steamcmd ${STEAMCMD_DIR}/linux32/steam \
    && ln -s ${STEAMCMD_DIR}/steamcmd.sh ${STEAMCMD_DIR}/steam.sh

WORKDIR ${STEAMCMD_DIR}
VOLUME ${STEAMCMD_DIR}
