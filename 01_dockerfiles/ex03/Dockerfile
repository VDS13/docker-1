FROM ubuntu:18.04
LABEL maintainer="dnichol@student.21-school.ru"
RUN apt-get update && \
apt-get upgrade -y && \
apt-get install -y ca-certificates openssh-server wget postfix
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh && sh script.deb.sh && apt-get install -y gitlab-ce
RUN apt update && apt install -y tzdata && \
apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
EXPOSE 443 80 22
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null
