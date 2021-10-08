FROM golang:alpine AS multistage
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
WORKDIR /usr/src/app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build

FROM scratch
WORKDIR /usr/src/app/
COPY --from=multistage /usr/src/app/server /usr/src/app/server
COPY --from=0 /etc/passwd /etc/passwd
EXPOSE 8080
ENV REQUEST_ORIGIN=http://localhost:5000

USER appuser

ENTRYPOINT ["/usr/src/app/server"]