FROM gwwfps/busybox-jsruntimes:base

ENV IOJS_VERSION 1.6.4

ENV PATH /iojs/bin:$PATH

RUN opkg-install curl ca-certificates libstdcpp \
  && curl -s https://iojs.org/dist/v$IOJS_VERSION/iojs-v$IOJS_VERSION-linux-x64.tar.gz | gunzip | tar -xf - -C / \
  && opkg-cl remove curl ca-certificates \
  && rm -rf /var/cache/apk/* \
  && mv /iojs-v$IOJS_VERSION-linux-x64 /iojs \
  && npm install -g npm \
  && npm cache clear

CMD ["iojs"]
