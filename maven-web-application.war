FROM ubuntu:latest

# Java Installation
RUN apt-get update && apt-get install -y openjdk-11-jdk

# Apache Installation
RUN apt-get install -y apache2 && apt-get install -y wget

# Tomcat9 Installation
RUN wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz && \
    tar xzf apache-tomcat-9.0.55.tar.gz && \
    rm apache-tomcat-9.0.55.tar.gz && \
    mv apache-tomcat-9.0.55 /var/lib/tomcat9
COPY . maven-web-application.war /var/lib/tomcat9/webapps/
EXPOSE 80
CMD service apache2 start && /var/lib/tomcat9/bin/catalina.sh run
