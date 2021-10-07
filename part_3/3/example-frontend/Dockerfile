FROM node:lts-alpine

EXPOSE 5000

WORKDIR /usr/src/app

COPY . .

ENV REACT_APP_BACKEND_URL=http://127.0.0.1:8080

RUN npm install && \ 
    npm install -g serve && \ 
    npm run build && \
    addgroup -g 1001 example && \
    adduser -S -u 1001 -G example example && \
    chown -R example:example /usr/src/app && \
    chmod 755 /usr/src/app
USER example

CMD  ["serve", "-s", "-l", "5000", "build"]