FROM debian 

ENV DEBIAN_FRONTEND noninteractive 

RUN apt-get update -q \
	&& apt-get install -yq --no-install-recommends \
	ca-certificates \
	openssh-server \
	postfix \
	curl \
	apt-transport-https \
	vim \
	tzdata 

# Expose web & ssh
		EXPOSE 443 80 22

RUN apt-get install sudo
RUN curl https://packages.gitlab.com/install/repositories/gitlabugitlab-ee/script.deb.sh | sudo bash
ENV external_url http://gitlab.example.com
RUN sudo EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ee
