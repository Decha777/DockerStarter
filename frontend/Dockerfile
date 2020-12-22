###########
# BUILDER #
###########

# pull official base image
FROM node:12.18.3-alpine3.9 as builder

# set work directory
WORKDIR /usr/src/app/

# install dependencies and avoid `node-gyp rebuild` errors
COPY ./react_app/package.json .

# copy our react project
COPY ./react_app .

RUN apk add --no-cache --virtual .gyp \
  && npm install \
  && apk del .gyp
