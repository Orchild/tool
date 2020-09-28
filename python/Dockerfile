FROM jenkins/ssh-slave:alpine

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g" /etc/apk/repositories

RUN apk --no-cache add git \
subversion \
python2 \
openblas \
libstdc++ \
libxml2 \
libxslt \
&& apk --no-cache add --virtual .build-deps \
gcc \
python2-dev \
build-base \
libxml2-dev \
libxslt-dev \
&& ln -s /usr/include/locale.h /usr/include/xlocale.h \
&& python -m ensurepip \
&& pip config set global.index-url http://mirrors.aliyun.com/pypi/simple \
&& pip config set install.trusted-host mirrors.aliyun.com \
&& pip install --no-cache-dir numpy \
&& pip install --no-cache-dir pyquery python-jenkins pymysql pandas pyyaml configparser \
&& apk del .build-deps
