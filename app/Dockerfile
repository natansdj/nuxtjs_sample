ARG NODE_ENV="12.0"

FROM node:$NODE_ENV

# Variables of nuxt configure
ENV HOST 0.0.0.0
ENV NUXT_PORT 3000

EXPOSE $NUXT_PORT

ENV APP_ROOT /src

RUN mkdir ${APP_ROOT}
WORKDIR ${APP_ROOT}
ADD . ${APP_ROOT}

# copy the app, note .dockerignore
RUN npm install

# build necessary, even if no static files are needed,
# since it builds the server as well
RUN npm run build
