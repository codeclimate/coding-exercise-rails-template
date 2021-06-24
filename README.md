# README


- clone this repo
- `bin/bundle install`
- `bin/rails spec` # to run tests
- `bin/bundle exec foreman start` # if you want to start up rails =)


# To reproduce this setup
steps borrowed from here, with a few extra tuning: https://relishapp.com/rspec/rspec-rails/docs/gettingstarted

Asusming a box with rails installed:
```sh
rails new coding-exercise
cd coding-exercise
echo 'gem "rspec-rails", group: [:development, :test]' >> Gemfile
echo 'gem "rexml"' >> Gemfile
echo 'gem "foreman"' >> Gemfile
sed -E -i "s/ruby '3.0.0'/ruby '~> 3'/" Gemfile
bin/bundle install
bin/rails generate rspec:install
bin/rails generate scaffold Exercise name:string
bin/rails db:migrate && rails db:test:prepare

echo "serve: bin/rails server" >> Procfile
echo "webpack: bin/webpack-dev-server" >> Procfile
```

You might want to drop a few extra files might not be cruicial or relevant for the exercise
