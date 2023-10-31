FROM --platform=linux/arm64/v8 node:18.18.2-bullseye-slim

RUN apk update && \
    apk add --no-cache docker-cli docker-cli-compose

WORKDIR /letsencrypt-docker-compose/cli
COPY package*.json ./
RUN npm ci --only=production
COPY . .
ENV NODE_ENV=production

WORKDIR /workdir

CMD ["node", "/letsencrypt-docker-compose/cli/src/app.js"]