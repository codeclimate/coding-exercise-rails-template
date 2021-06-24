# README


- clone this repo
- `bundle install`
- `rspec`
- `rails s` # if you want to start up rails =)


# To reproduce this setup
steps borrowed from here, with a few extra tuning: https://relishapp.com/rspec/rspec-rails/docs/gettingstarted

Asusming a box with rails installed:
```sh
rails new coding-exercise
cd coding-exercise
echo 'gem "rspec-rails", group: [:development, :test]' >> Gemfile
echo 'gem "rexml"' >> Gemfile
sed -E -i "s/ruby '3.0.0'/ruby '~> 3'/" Gemfile
bundle install
rails generate rspec:install
rails generate scaffold Exercise name:string
rails db:migrate && rails db:test:prepare
rspec
```

You might want to drop a few extra files might not be cruicial or relevant for the exercise
