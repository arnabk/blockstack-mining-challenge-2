FROM debian

RUN apt update
RUN apt install wget tar -y
RUN wget https://bitcoin.org/bin/bitcoin-core-0.20.1/bitcoin-0.20.1-x86_64-linux-gnu.tar.gz
RUN gzip -d bitcoin-0.20.1-x86_64-linux-gnu.tar.gz
RUN tar xvf bitcoin-0.20.1-x86_64-linux-gnu.tar
RUN rm -f bitcoin-0.20.1-x86_64-linux-gnu.tar
RUN mkdir /data

COPY bitcoin.conf /root

VOLUME /data

ENTRYPOINT [ "/bitcoin-0.20.1/bin/bitcoind", "-conf=/root/bitcoin.conf", "-datadir=/data" ]
