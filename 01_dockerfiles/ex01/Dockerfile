FROM debian
ENV TS3SERVER_LICENSE=accept
LABEL maintainer="dnichol@student.21-school.ru"
EXPOSE 9987/udp 10011 30033
WORKDIR /home/ts3
RUN apt-get update -y && apt-get upgrade -y && apt-get install wget bzip2 -y
RUN wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.1.1.tar.bz2 && rm teamspeak3-server_linux_amd64-3.1.1.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT sh ts3server_minimal_runscript.sh
