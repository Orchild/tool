FROM jenkins-slave/python:debian

RUN apt install -y perl \
dpkg \
&& dpkg --add-architecture i386 \
&& apt-get update \
&& apt-get install -y wine32

RUN wget -nc https://dl.winehq.org/wine-builds/winehq.key \
&& apt-key add winehq.key \
&& echo "deb https://dl.winehq.org/wine-builds/debian/ buster main" >> /etc/apt/sources.list \
&& apt update

COPY *.deb ./
RUN apt install -y libsdl2-2.0 \ 
&& dpkg -i libfaudio0_19.07-0_bionic_amd64.deb \
&& dpkg -i libfaudio0_19.07-0_bionic_i386.deb

RUN apt install -y wine-stable-i386
RUN apt install -y wine-stable-amd64
RUN apt install -y wine-stable
RUN apt install -y winehq-stable

RUN rm -rf /var/lib/apt/lists/* *.deb

RUN winecfg > /dev/null 2>&1