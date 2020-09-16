FROM node:12-alpine

RUN apk add --no-cache git openssh-client

RUN yarn global add expo-cli@3.27.4 sharp-cli@1.13.1 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
