ARG SANDSTORM_BASE_TAG=latest
FROM encoren1/gameserver:sandstorm-${SANDSTORM_BASE_TAG}

ENV APP_SERVER_PORT 27102
ENV APP_SERVER_QUERYPORT 27131 
ENV APP_SERVER_MAXPLAYERS 10
ENV APP_SERVER_MAP Oilfield?Scenario=Scenario_Refinery_Push_Security

ENV APP_SERVER_NAME SandstormServer
ENV APP_SERVER_PASSWORD serverpassword
ENV APP_SERVER_RCONPASSWORD rconpassword

ENV APP_EXTRA_ARGS ""

EXPOSE ${APP_SERVER_PORT}
EXPOSE ${APP_SERVER_PORT}/udp
EXPOSE ${APP_SERVER_QUERYPORT}/udp

#
CMD ["/bin/run_server_ue4"]
