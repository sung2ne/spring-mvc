FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# JDK 8 설치
RUN apt-get update && \
    apt-get install -y openjdk-8-jdk && \
    update-alternatives --set java /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java

# Maven 설치
RUN apt-get install -y maven

# MariaDB 11.4.5 설치 (공식 레포 사용)
RUN apt-get install -y software-properties-common gnupg && \
    curl -LsS https://r.mariadb.com/downloads/mariadb_repo_setup | bash && \
    apt-get update && \
    apt-get install -y mariadb-server

# phpMyAdmin 설치
RUN apt-get install -y phpmyadmin apache2 php libapache2-mod-php php-mysql

# Apache2 서비스 활성화 및 MariaDB 기본설정
RUN service apache2 restart

# 포트 노출
EXPOSE 3306 8080 80