source "https://rubygems.org"
git_source(:github) { |name| "https://github.com/#{name}.git" }

# Specify your gem's dependencies in sentry-ruby.gemspec
gemspec
gem 'sentry-ruby', git: 'git@github.com:ifad/sentry-legacy-ruby.git'

gem "rake", "~> 12.0"
gem "rspec", "~> 3.0"
gem 'simplecov'
gem "simplecov-cobertura", "~> 1.4"
gem "rexml"
# https://github.com/flavorjones/loofah/pull/267
# loofah changed the required ruby version in a patch so we need to explicitly pin it
gem "loofah", "2.20.0" if RUBY_VERSION.to_f < 2.5

# For https://github.com/ruby/psych/issues/655
gem "psych"
redis_rb_version = ENV.fetch("REDIS_RB_VERSION", "5.0")
gem "redis", "~> #{redis_rb_version}"

sidekiq_version = ENV["SIDEKIQ_VERSION"]
sidekiq_version = "6.0" if sidekiq_version.nil?
sidekiq_version = Gem::Version.new(sidekiq_version)

gem "sidekiq", "~> #{sidekiq_version}"

rails_version = ENV.fetch("RAILS_VERSION", "6.0")
gem "rails", "~> #{rails_version}"

if RUBY_VERSION.to_f >= 2.6
  gem "debug", github: "ruby/debug", platform: :ruby
  gem "irb"
end

gem "pry"
