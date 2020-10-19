FROM jenkins/ssh-slave

RUN sed -i "s/deb.debian.org/mirrors.aliyun.com/g" /etc/apt/sources.list

RUN apt update \
&& apt install -y git \
subversion \
python-pip\
&& pip config set global.index-url http://mirrors.aliyun.com/pypi/simple \
&& pip config set install.trusted-host mirrors.aliyun.com \
&& pip install --no-cache-dir numpy \
&& pip install --no-cache-dir pyquery python-jenkins pymysql pandas pyyaml configparser
