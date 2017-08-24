FROM gradle:jdk8
MAINTAINER Surittec <surittec.com.br>

# Comeback to root, gradle image uses USER gradle
USER root

# Install python pip
RUN \
	apt-get update && \
	apt-get install -y python-pip

# Install EB CLI
RUN pip install awsebcli --upgrade

# Define default command.
CMD ["bash"]
