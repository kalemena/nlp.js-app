FROM node:10

COPY [ ".", "/opt/nlpjs-app/" ]

WORKDIR /opt/nlpjs-app/

RUN npm install

# COPY [ "./docker/nlpjs-app/.env-base", "/opt/nlpjs-app/.env" ]
# COPY [ "./docker/nlpjs-app/.env-client", "/opt/nlpjs-app/client/.env" ]

# Rebuild to use port 3010
# RUN cd /opt/nlp-app/client \
#     && npm run build --skip-test \
#     && cd /opt/nlp-app/ \
#     && rm public \
#     && mv client/build public

CMD npm start