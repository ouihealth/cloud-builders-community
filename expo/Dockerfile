FROM node:16.9.1-alpine

RUN apk add --no-cache git openssh-client make gcc g++ python3

RUN yarn global add expo-cli@4.12.1 sharp-cli@1.15.0 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
