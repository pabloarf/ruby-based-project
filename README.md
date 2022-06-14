# README

* Ruby version

`2.7.5`

* System dependencies

Rails version = `6.1.3.1`

* Configuration

## Setup

* Rename `rubybase` with `project_name`

* Create a `.env` file

```
cp .env.sample .env
```

## Run with docker
```
bin/dev bash
```

## Run console

```
sh script/console.sh
```

## Run server

```
sh script/server.sh
```

## Create new rails project
```
# -T no tests
# Use sprockets for assets
bundle exec rails new . -T --database=postgresql --skip-webpack-install
```

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
