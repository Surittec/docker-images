FROM gradle:jdk8
MAINTAINER Surittec <surittec.com.br>

# Comeback to root, gradle image uses USER gradle
USER root

# Install python pip and npm
RUN \
	apt-get update && \
	curl -sL https://deb.nodesource.com/setup_6.x | bash - && \
	apt-get install -y python-pip nodejs build-essential
	
# Install EB CLI
RUN pip install awsebcli --upgrade

# Define default command.
CMD ["bash"]
