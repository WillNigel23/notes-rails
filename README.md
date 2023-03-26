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


## Install Tailwind CSS
`bundle add tailwindcss-rails`
`rails tailwindcss:install`

To Force Auto-update of Tailwind Changes
Add `gem "rails_live_reload"` to Gemfile under `group :development do`
Create initializer config/initializers/rails_live_reload.rb:
```
RailsLiveReload.configure do |config|
  # config.url = "/rails/live/reload"

  # Default watched folders & files
  # config.watch %r{app/views/.+\.(erb|haml|slim)$}
  # config.watch %r{(app|vendor)/(assets|javascript)/\w+/(.+\.(css|js|html|png|jpg|ts|jsx)).*}, reload: :always

  # More examples:
  # config.watch %r{app/helpers/.+\.rb}, reload: :always
  # config.watch %r{config/locales/.+\.yml}, reload: :always

  # config.enabled = Rails.env.development?
end if defined?(RailsLiveReload)

```
Run
`bundle binstubs --all`



## Start Rails App
For Linux
`rails server`
or
For Windows
Change first Procfile.dev to
```
web: ruby bin/rails server -p 3000
css: ruby bin/rails tailwindcss:watch

```
`bash bin/dev`

