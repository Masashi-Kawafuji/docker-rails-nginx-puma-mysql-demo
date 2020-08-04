FROM ruby:2.7.1

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
  echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
  apt-get update -qq && \
  apt-get install -y nodejs yarn build-essential libpq-dev

RUN mkdir /rails-with-nginx
WORKDIR /rails-with-nginx

COPY Gemfile Gemfile.lock ./
RUN bundle install

COPY . ./

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3000


CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]