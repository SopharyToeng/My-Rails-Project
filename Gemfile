source 'https://rubygems.org'

git_source(:github) do |repo_name|
  repo_name = "#{repo_name}/#{repo_name}" unless repo_name.include?("/")
  "https://github.com/#{repo_name}.git"
end

gem 'rails',            '~> 5.0.2'
gem 'pg',               '~> 0.20.0'
gem 'puma',             '~> 3.0'
gem 'sass-rails',       '~> 5.0'
gem 'uglifier',         '>= 1.3.0'
gem 'coffee-rails',     '~> 4.2'
gem 'jquery-rails'
gem 'turbolinks',       '~> 5'
gem 'jbuilder',         '~> 2.5'
gem 'dotenv-rails',     '~> 2.2'
gem 'haml',             '~> 4.0', '>= 4.0.7'
gem 'simple_form',      '~> 3.4'
gem 'materialize-sass', '~> 0.98.0'
gem 'material_icons',   '~> 2.2', '>= 2.2.1'
gem 'activemodel-serializers-xml', github: 'rails/activemodel-serializers-xml'
gem 'draper',           github: 'audionerd/draper', branch: 'rails5'

group :development, :test do
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

group :test do
  gem 'shoulda-matchers', '~> 3.1', '>= 3.1.1'
end

group :development do
  gem 'web-console',           '>= 3.3.0'
  gem 'listen',                '~> 3.0.5'
  gem 'spring'
  gem 'spring-watcher-listen', '~> 2.0.0'
  gem 'rubocop',               '~> 0.47.1', require: false
  gem 'brakeman',              '~> 3.5', require: false
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
