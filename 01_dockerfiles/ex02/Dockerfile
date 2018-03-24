FROM ruby

# Update and install dependencies
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

# Install rails
RUN gem update
RUN gem install rails

# Open ports
EXPOSE 3000

RUN mkdir /opt/app
# Onbuild command
ONBUILD WORKDIR /opt/app/
ONBUILD ADD . /opt/app/

ONBUILD RUN bundle install && \
			rake db:migrate && \
			rake db:seed
