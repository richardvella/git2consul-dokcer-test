FROM alpine:latest

RUN apk --update add nodejs nodejs-npm git openssh curl && \
    rm -rf /var/cache/apk/* && \
    git config --global http.sslVerify false

RUN git clone https://github.com/Cimpress-MCP/git2consul.git /g2c && \
    cd g2c && \
    npm install --global && \
    mkdir -p /etc/git2consul.d

RUN git clone https://github.com/knieschraube/git2consul-docker.git /gtc-d && \
    cp gtc-d/wait_for_consul_leader.sh /

ENTRYPOINT [ "/usr/bin/node", "/usr/lib/node_modules/git2consul" ]
