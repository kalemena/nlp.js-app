FROM node:10

# Pre-requisits
RUN apt-get -y update \
    && apt-get -y install libgl1 \
# Cleanup (reduce size)
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY [ ".", "/opt/nlpjs-app/" ]

WORKDIR /opt/nlpjs-app/

COPY [ "./docker/nlpjs-app/.env-base", "/opt/nlpjs-app/.env" ]
COPY [ "./docker/nlpjs-app/.env-client", "/opt/nlpjs-app/client/.env" ]

# Rebuild *client*
RUN cd /opt/nlpjs-app/client \
    && npm i \
    && npm run build \
    && cd /opt/nlpjs-app/ \
    && mv client/build public

RUN npm install

CMD npm start