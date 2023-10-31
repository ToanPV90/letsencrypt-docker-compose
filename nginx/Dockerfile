FROM --platform=linux/arm64/v8 nginx:1.23-alpine3.17

RUN apk add --no-cache openssl jq

WORKDIR /letsencrypt-docker-compose

COPY config-nginx.sh start-nginx.sh ./
RUN chmod +x config-nginx.sh start-nginx.sh

EXPOSE 80

CMD ["/letsencrypt-docker-compose/start-nginx.sh"]