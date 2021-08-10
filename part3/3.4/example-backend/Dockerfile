FROM ubuntu:latest

WORKDIR /usr/src

COPY . .

RUN apt-get update && apt-get install -y wget gcc \ 
    && rm -rf /usr/local/go && wget -c https://golang.org/dl/go1.16.3.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.16.3.linux-amd64.tar.gz && go build && go test && useradd -m /bin/bash appuser

USER appuser

ENV REQUEST_ORIGIN http://localhost:5000

EXPOSE 8080

CMD ./server