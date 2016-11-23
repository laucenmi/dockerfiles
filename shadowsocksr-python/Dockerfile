#
# Dockerfile for shadowsocksr
#

FROM python:alpine
MAINTAINER aofa <laucenmi@qq.com>

RUN apk add --no-cache libsodium
RUN pip --no-cache-dir install https://github.com/breakwa11/shadowsocks/archive/manyuser.zip

ENV SERVER_ADDR "0.0.0.0"
ENV SERVER_IPV6 "::"
ENV SERVER_PORT 8080
ENV METHOD "aes-256-cfb"
ENV PASSWORD "123456"
ENV PROTOCOL "auth_sha1_v4_compatible"
ENV OBFS "tls1.2_ticket_auth_compatible"
ENV TIMEOUT 300
ENV WORKERS 4

CMD ssserver -s "$SERVER_ADDR"		\
             -p "$SERVER_PORT"		\
             -k "$PASSWORD"			\
             -m "$METHOD"			\
             -O "$PROTOCOL"			\
             -o "$OBFS"				\
             -t "$TIMEOUT"			\
             --workers "$WORKERS"	\
             --fast-open