ARG STEAMCMD_TAG=latest
FROM my-steamcmd:${STEAMCMD_TAG}

ARG STEAM_USER=anonymous
ARG STEAMCMD_TAG=latest
ARG STEAM_PASSWORD
ARG APPID
ARG APPNAME

ENV APPID $APPID
ENV APPNAME $APPNAME
ENV STEAM_USER $STEAM_USER
ENV STEAM_PASSWORD $STEAM_PASSWORD

COPY run_server /bin/run_server

VOLUME ["/home/steam/${APPID}"]
RUN /bin/install_appid


COPY merge_config /bin/merge_config
COPY install_appid /bin/install_appid
