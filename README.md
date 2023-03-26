# notes-rails
Notes web app made in rails.


## Installing Rails
`sudo gem install rails -v 6.0.2.1`

## Initialize Rails App
`rails new notes_app`
or
`rails new notes_app -d=postgresql`

## Setup Figaro
Figaro is used to keep env variables stored securely
Add `gem "figaro"` to Gemfile
`bundle exec figaro install`

Set env variables at config/application.yml as key value pair
`SECRET_KEY: secretkey`

Usage
`ENV["SECRET_KEY"]`


## Setup DB
Setup config/database.yml file
Add username and password to `default`

If using linux, make sure to change pg_hba.conf by adding
`local  <database>  <user>              md5`

Run to create db
`rails db:create`


## Migrate DB
`rails db:migrate`

## Start Rails App
`rails server`