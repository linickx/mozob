# tls-observatory database

FROM postgres

RUN apt-get update
RUN apt-get install -y curl

RUN curl -o /docker-entrypoint-initdb.d/schema.sql https://raw.githubusercontent.com/mozilla/tls-observatory/master/database/schema.sql
ADD schema.sql.docker.sql /docker-entrypoint-initdb.d/