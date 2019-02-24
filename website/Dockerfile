FROM node

MAINTAINER https://github.com/mozilla/http-observatory-website

RUN groupadd --gid 1001 app && \
    useradd --uid 1001 --gid 1001 -d /home/app --shell /usr/sbin/nologin app

WORKDIR /home/app
RUN chown app /home/app
USER app

ARG HTTP_OBS
ARG TLS_OBS
ENV HTTP_OBS=$HTTP_OBS
ENV TLS_OBS=$TLS_OBS

RUN git clone https://github.com/mozilla/http-observatory-website .

RUN echo "HTTP_OBS: $HTTP_OBS"
RUN echo "TLS_OBS: $TLS_OBS"

RUN sed -i "s|https://http-observatory.security.mozilla.org/api/v1/|$HTTP_OBS|g" /home/app/src/js/observatories/http.js
RUN grep 'API_URL' /home/app/src/js/observatories/*.js
RUN sed -i "s|https://http-observatory.security.mozilla.org/api/v1/|$HTTP_OBS|g" /home/app/src/js/constants.js
RUN sed -i "s|https://tls-observatory.services.mozilla.com/api/v1/|$TLS_OBS|g" /home/app/src/js/constants.js
RUN grep 'api/v1' /home/app/src/js/*.js

RUN npm install

EXPOSE 5500
CMD [ "npm", "run", "watch" ]