FROM node:18.18.2-alpine

RUN apk add --no-cache git openssh-client make gcc g++ python3

RUN yarn global add expo-cli@5.0.3 https://github.com/ouihealth/sharp-cli\#c2f4543 sharp-cli@1.15.0 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
