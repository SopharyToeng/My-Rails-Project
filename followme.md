1/ Generate App
  - rails new appname -d postgresql -T

2/ Update pg version and database.yml
  - change pg version and add gem 'dotenv-rails', '~> 2.2' in Gemfile
  - create .env.example
  - Update database.yml to
    ##default: &default
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
  - detail about dotenv: https://github.com/bkeepers/dotenv

3/ add haml and Simple form
  - add these in Gemfile
    . gem 'haml', '~> 4.0', '>= 4.0.7' &
    . gem 'simple_form', '~> 3.4'
  - bundle
  - rails generate simple_form:install --bootstrap
  ** simple form detail: https://github.com/plataformatec/simple_form

4/ add asset gem(materialize) and drapper
  - add these in Gemfile
    . gem 'materialize-sass', '~> 0.98.0'
    . gem 'material_icons',   '~> 2.2', '>= 2.2.1'
    . gem 'draper',           github: 'audionerd/draper', branch: 'rails5'
  - bundle
5/ add rspec and configuration
  - add these in Gemfile
    ##group :development, :test do
      gem 'byebug',             platform: :mri
      gem 'pry',                '~> 0.10.4'
      gem 'rspec-rails',        '~> 3.5', '>= 3.5.2'
      gem 'ffaker',             '~> 2.5'
      gem 'launchy',            '~> 2.4', '>= 2.4.3'
      gem 'capybara',           '~> 2.13'
      gem 'poltergeist',        '~> 1.14'
      gem 'database_cleaner',   '~> 1.5', '>= 1.5.3'
      gem 'factory_girl_rails', '~> 4.8'
    end
  - bundle
  - rails generate rspec:install
  - detail about rspec: https://github.com/rspec/rspec-rails
6. add robocop and brakeman
  - add these in Gemfile
    .  gem 'rubocop',               '~> 0.47.1', require: false
    .  gem 'brakeman',              '~> 3.5', require: false
  - Detail about robocop and brakeman
    . https://github.com/pjkelly/robocop
    . https://github.com/presidentbeef/brakeman

