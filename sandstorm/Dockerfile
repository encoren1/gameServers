ARG SANDSTORM_BASE_TAG=latest
FROM encoren1/gameserver:sandstorm-${SANDSTORM_BASE_TAG}

ENV APP_SRCDS_FLAGS ""
ENV APP_SERVER_PORT 27102
ENV APP_SERVER_QUERYPORT 27131 
ENV APP_SERVER_MAXPLAYERS 28
ENV APP_SERVER_MAP market_coop
ENV APP_SERVER_NAME SandstormServer
ENV APP_SERVER_PASSWORD serverpassword
ENV APP_SERVER_RCONPASSWORD rconpassword
ENV USE_SRCDS true

EXPOSE ${APP_SERVER_PORT}
EXPOSE ${APP_SERVER_PORT}/udp
EXPOSE ${APP_SERVER_QUERYPORT}
EXPOSE ${APP_SERVER_QUERYPORT}/udp

#Insurgency/Binaries/Linux/InsurgencyServer-Linux-Shipping Oilfield?Scenario=Scenario_Refinery_Push_Security \
#?MaxPlayers=28 -Port=27102 -QueryPort=27131 -log -hostname="My Server"
#CMD ["/bin/run_server"]
CMD ["/home/steam/581330/Insurgency/Binaries/Linux/InsurgencyServer-Linux-Shipping", "-hostname=Dev_test"]
