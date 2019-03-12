# README

```ruby
# build image
docker-compose build

# bundle
docker-compose run -u root backend bundle

# create database
docker-compose run backend bundle exec rails db:create db:migrate db:seed

# start
docker-compose up
```

New project need to add `db (docker-compose.yml mysql name)` to `database.yml`

```ruby
default: &default
  adapter: mysql2
  encoding: utf8
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  host: db
  port: 3306
  username: root
  password: password
  socket: /tmp/mysql.sock
```
