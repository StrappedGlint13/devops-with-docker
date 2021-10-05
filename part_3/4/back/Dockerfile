FROM golang:alpine AS multistage

WORKDIR /go/src/api

COPY . .

RUN go build

FROM alpine:3.8
WORKDIR /usr/src/app
COPY --from=multistage /go/src/api .
EXPOSE 8080
ENV REQUEST_ORIGIN=http://localhost:5000

RUN addgroup -g 1001 example && \
    adduser -S -u 1001 -G example example && \
    chown -R example:example /usr/src/app && \
    chmod 755 /usr/src/app
USER example

CMD ./server