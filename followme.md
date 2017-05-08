1/ Generate App
  -rails new appname -d postgresql -T

2/ Update pg version and database.yml
  - change pg version and add gem 'dotenv-rails', '~> 2.2' in Gemfile
  - create .env.example
  - Update database.yml to
    default: &default
      adapter: postgresql
      pool: 5
      timeout: 5000
      username: <%= ENV['DATABASE_USERNAME'] %>
      password: <%= ENV['DATABASE_PASSWORD'] %>

    development:
      <<: *default
      database: <%= ENV['DATABASE_NAME'] %>_development

    test:
      <<: *default
      database: <%= ENV['DATABASE_NAME'] %>_test

    staging:
      <<: *default
      database: <%= ENV['DATABASE_NAME'] %>

    production:
      <<: *default
      database: <%= ENV['DATABASE_NAME'] %>
3/ add haml and Simple form
  - add gem 'haml', '~> 4.0', '>= 4.0.7'
        gem 'simple_form', '~> 3.4'  in Gemfile
  - bundle
  - rails generate simple_form:install --bootstrap
  ** simple form detail: https://github.com/plataformatec/simple_form
