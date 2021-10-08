FROM node:alpine as build-stage
COPY . .
RUN npm install && \
    npm run build

FROM node:alpine
RUN npm install -g serve
WORKDIR /usr/src/app
COPY --from=build-stage /build /usr/src/app/build
EXPOSE 5000
ENV REACT_APP_BACKEND_URL=http://127.0.0.1:8080

RUN	chown node -R /usr/src/app
USER node

CMD  ["serve", "-s", "-l", "5000", "build"]