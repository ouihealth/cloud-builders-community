FROM node:12-alpine

RUN apk add --no-cache git openssh-client

RUN yarn global add expo-cli@3.20.1 sharp-cli@1.13.1 firebase-tools@8.4.3 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

ADD firebase.bash /usr/bin

RUN chmod +x /usr/bin/firebase.bash

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
