FROM node:14-alpine

ARG NODE_ENV=production
ENV NODE_ENV=$NODE_ENV

WORKDIR /usr/src/app

COPY yarn.lock .
COPY package.json .

RUN set -ex; \
  if [ "$NODE_ENV" = "production" ]; then \
    yarn install --no-cache --frozen-lockfile --production; \
  elif [ "$NODE_ENV" = "test" ]; then \
    yarn install --no-cache; \
  fi;

COPY . .

EXPOSE 3000

CMD [ "yarn", "start" ]