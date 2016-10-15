#
# Dockerfile for shadowsocks
#

FROM python:alpine
MAINTAINER aofa <laucenmi@qq.com>

RUN pip install shadowsocks

ENV SERVER_ADDR 0.0.0.0
ENV SERVER_PORT 8080
ENV METHOD aes-256-cfb
ENV PASSWORD 123456
ENV TIMEOUT 300
ENV WORKERS 4

//arukas.io
#EXPOSE $SERVER_PORT/tcp

CMD ssserver -s "$SERVER_ADDR"		\
             -p "$SERVER_PORT"		\
             -k "$PASSWORD"			\
             -m "$METHOD"			\
             -t "$TIMEOUT"			\
             --workers "$WORKERS"	\
             --fast-open
