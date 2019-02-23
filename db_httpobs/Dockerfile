# http-observatory database

FROM postgres

RUN apt-get update
RUN apt-get install -y curl

RUN curl -o /docker-entrypoint-initdb.d/schema.sql https://raw.githubusercontent.com/mozilla/http-observatory/master/httpobs/database/schema.sql
RUN curl -o /docker-entrypoint-initdb.d/schema.sql.docker.sql https://raw.githubusercontent.com/mozilla/http-observatory/master/httpobs/database/schema.sql.docker.sql
