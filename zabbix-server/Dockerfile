ARG ZABBIX_BASE=ol
ARG ZABBIX_VERSION=5.2.7
FROM zabbix/zabbix-server-pgsql:${ZABBIX_BASE}-${ZABBIX_VERSION}

USER root

RUN microdnf install -y telnet wget python36
RUN microdnf install -y bind bind-utils
RUN microdnf install -y unixODBC unixODBC-devel
RUN microdnf install -y postgresql-odbc

COPY requirements.txt /requirements.txt

RUN python3 -m pip install -r /requirements.txt

USER 1997