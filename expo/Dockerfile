FROM node:12-alpine

RUN yarn global add expo-cli@3.16.1 sharp-cli@1.13.1

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
