#rspec #test

테스트 DB 마이그레이션 안될 때 명령어
```ruby
bundle exec rake db:drop RAILS_ENV=test
bundle exec rake db:create RAILS_ENV=test
bundle exec rake db:schema:load RAILS_ENV=test
```

