FROM ubuntu:18.04

EXPOSE 5000

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_lts.x | bash - && \
    apt install -y nodejs && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/* 

COPY . .

ENV REACT_APP_BACKEND_URL=http://127.0.0.1:8080

RUN npm install && \ 
    npm install -g serve && \ 
    npm run build && \ 
    groupadd docker && \
    useradd -m example && \
    usermod -aG docker example && \
    chown example .
USER example

CMD  ["serve", "-s", "-l", "5000", "build"]