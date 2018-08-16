FROM  java:latest
MAINTAINER Jerry

ADD apache-maven-3.5.3 /usr/local/maven3
ENV MAVEN_HOME  /usr/local/maven3
ENV PATH $PATH:$MAVEN_HOME/bin
RUN mkdir -p $MAVEN_HOME

ADD apache-tomcat-8.5.31  /usr/local/tomcat8
ENV CATALINA_HOME /usr/local/tomcat8
ENV PATH $PATH:$CATALINA_HOME/bin
RUN mkdir -p $CATALINA_HOME

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

WORKDIR $CATALINA_HOME
RUN mvn -version
EXPOSE 8080

CMD ["/usr/local/tomcat8/bin/catalina.sh", "run"]
