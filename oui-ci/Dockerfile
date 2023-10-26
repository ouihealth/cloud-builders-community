FROM node:18.18.2-alpine

RUN apk add --no-cache git openssh-client curl make gcc g++ python3 libc6-compat \
      # https://github.com/CircleCI-Public/gcp-cli-orb/issues/21#issuecomment-709539907
      bash python3-dev

# install jq
RUN JQ_URL="https://circle-downloads.s3.amazonaws.com/circleci-images/cache/linux-amd64/jq-latest" \
  && curl --silent --show-error --location --fail --retry 3 --output /usr/bin/jq $JQ_URL \
  && chmod +x /usr/bin/jq \
  && jq --version

RUN yarn global add expo-cli@5.0.3 https://github.com/ouihealth/sharp-cli\#c2f4543 firebase-tools@12.5.2 lerna@3.22.1 --verbose --no-cache --production --ignore-optional && \
      yarn cache clean

ADD firebase.bash /usr/bin

RUN chmod +x /usr/bin/firebase.bash

ENV NODE_OPTIONS="--max-old-space-size=4096"

ENTRYPOINT [ "expo" ]
