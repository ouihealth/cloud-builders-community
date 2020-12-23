FROM node:12-alpine

RUN apk add --no-cache git openssh-client

RUN yarn global add expo-cli@3.27.4 sharp-cli@1.13.1 firebase-tools@8.4.3 lerna@3.22.1 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

# install jq
RUN JQ_URL="https://circle-downloads.s3.amazonaws.com/circleci-images/cache/linux-amd64/jq-latest" \
  && curl --silent --show-error --location --fail --retry 3 --output /usr/bin/jq $JQ_URL \
  && chmod +x /usr/bin/jq \
  && jq --version

ADD firebase.bash /usr/bin

RUN chmod +x /usr/bin/firebase.bash

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
