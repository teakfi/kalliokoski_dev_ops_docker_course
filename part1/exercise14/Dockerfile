FROM ruby:2.6.0

RUN bundle config --global frozen 1
RUN apt-get update && apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs

EXPOSE 3000

WORKDIR /app
RUN gem install bundler
RUN git clone https://github.com/docker-hy/rails-example-project
WORKDIR /app/rails-example-project
RUN bundle install
RUN rails db:migrate
CMD ["rails", "s"]
