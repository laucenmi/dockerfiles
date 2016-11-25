#
# Dockerfile for shadowsocksr
#

FROM python:alpine
MAINTAINER aofa <laucenmi@qq.com>

ENV KCP_VER 20161118
RUN apk add --no-cache libsodium wget supervisor openssh\
    && rm  -rf /tmp/* /var/cache/apk/*

RUN pip --no-cache-dir install https://github.com/breakwa11/shadowsocks/archive/manyuser.zip
RUN cd /root
    && wget https://github.com/xtaci/kcptun/releases/download/v$KCP_VER/kcptun-linux-amd64-$KCP_VER.tar.gz -O kcptun.tar.gz \
	&& tar xz kcptun.tar.gz \
    && rm client_linux_amd64

ADD supervisord.conf /etc/supervisord.conf
ADD kcptun.json /root/kcptun.json
ADD ssr.json /root/ssr.json

ADD sshd.sh /usr/local/bin/sshd.sh
ENTRYPOINT ["sshd.sh"]

CMD ["supervisord", "-n"]