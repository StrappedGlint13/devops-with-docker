FROM ubuntu:18.04

EXPOSE 5000

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt install -y nodejs

COPY . .

ENV REACT_APP_BACKEND_URL=http://127.0.0.1:8080

RUN npm install
RUN npm install -g serve

RUN npm run build

RUN groupadd docker
RUN useradd -m example
RUN usermod -aG docker example
RUN chown example .
USER example

CMD  ["serve", "-s", "-l", "5000", "build"]