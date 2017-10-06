FROM node:8.6.0-slim

# easy-mock
RUN \
  cd /var && wget https://github.com/hbrls/easy-mock/archive/docker-1.3.0.tar.gz && \
  tar -zxvf /var/docker-1.3.0.tar.gz -C /var && rm /var/docker-1.3.0.tar.gz && \
  mv /var/easy-mock-docker-1.3.0 /var/easy-mock

EXPOSE 7300

# npm install
RUN buildDeps='git make g++' && \
  apt-get update && apt-get install -y $buildDeps && \
  cd /var/easy-mock && npm install --no-optional && npm install mv@2.1.1 \
  npm cache clean --force && \
  npm run build && \
  apt-get purge -y --auto-remove $buildDeps && \
  rm -rf /var/lib/apt/lists/*

ENV NODE_ENV production
WORKDIR /var/easy-mock


CMD ["/usr/local/bin/node", "/var/easy-mock/app.js"]
