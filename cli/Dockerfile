FROM node:14-alpine

ENV APP_ROOT /home/node/app

RUN mkdir -p ${APP_ROOT}/node_modules \
 && chown -R node:node ${APP_ROOT}

WORKDIR ${APP_ROOT}

COPY package.json yarn.lock ./

USER node

RUN yarn --ignore-optional

COPY --chown=node:node . .

EXPOSE 3000

CMD ["yarn", "start"]
