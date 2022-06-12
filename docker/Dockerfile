FROM ruby:2.7.5-alpine as runtime

ENV HOME /root
ENV APP_HOME /var/www/app

# Install required packages
RUN apk add --no-cache \
    bash \
    build-base \
    curl-dev \
    git \
    linux-headers \
    postgresql-client \
    postgresql-dev \
    tzdata \
    tini

# Set the working directory
WORKDIR $APP_HOME

FROM runtime as application

# Add the Gemfile and Gemfile.lock into the image
ADD Gemfile* $APP_HOME/

# Install Ruby dependencies
RUN bundle install

# The application's $APP_HOME is going to be the user's $HOME
ENV HOME /var/www/app

# COPY app to container
COPY . $APP_HOME

EXPOSE 3000

ENTRYPOINT ["tini", "--"]

CMD ["bundle", "exec", "rails", "server", "-b", "0.0.0.0"]
