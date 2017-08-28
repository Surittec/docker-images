FROM openjdk:8-jdk
MAINTAINER Surittec <surittec.com.br>

# Install unzip, python pip and npm
RUN \
        apt-get update && \
        curl -sL https://deb.nodesource.com/setup_6.x | bash - && \
        apt-get install -y unzip python-pip nodejs build-essential

#Install gralde
ENV GRADLE_VERSION=3.5.1

RUN \
    mkdir /opt/gradle && \
    cd /opt/gradle && \
    curl -L https://services.gradle.org/distributions/gradle-$GRADLE_VERSION-bin.zip -o gradle-$GRADLE_VERSION-bin.zip && \
    unzip gradle-$GRADLE_VERSION-bin.zip && \
    rm gradle-$GRADLE_VERSION-bin.zip

ENV GRADLE_HOME=/opt/gradle/gradle-$GRADLE_VERSION
ENV PATH=$PATH:$GRADLE_HOME/bin
	
# Install EB CLI
RUN pip install awsebcli --upgrade

# Define default command.
CMD ["bash"]
