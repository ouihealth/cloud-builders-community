FROM node:12-alpine

RUN yarn global add expo-cli@3.18.2 sharp-cli@1.13.1

RUN apk add --no-cache git openssh-client

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
