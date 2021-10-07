FROM golang:alpine 

WORKDIR /usr/src/app

COPY . .

RUN go build

EXPOSE 8080
ENV REQUEST_ORIGIN=http://localhost:5000

RUN addgroup -g 1001 example && \
    adduser -S -u 1001 -G example example && \
    chown -R example:example /usr/src/app && \
    chmod 755 /usr/src/app
USER example

CMD ./server