FROM ubuntu:18.04
COPY web.sh .
RUN apt-get update && apt-get install -y curl
RUN chmod +x web.sh
CMD ./web.sh