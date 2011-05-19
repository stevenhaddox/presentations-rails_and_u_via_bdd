!SLIDE smbullets incremental transition=zoom
## Setup ##

  * Install Ruby 1.9.2 (we're using RVM, http://bit.ly/ruby-rvm)
  * Install RubyGems (RVM does this for free, or http://rubygems.org)
  * Install the Rails gem (3.0.7 currently)
  * Create your new Rails application ('u')
  * Why 'u'? It's short for uRL Shortener
  * Then create your .rvmrc project file so RVM knows which Ruby & gemset to use
  * Let's walk through it…

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>

!SLIDE code incremental transition=uncover
## Setup Commands: ##

    @@@sh
    # Install & Setup RVM
    $ rvm install 1.9.2
    $ rvm use 1.9.2
    $ rvm gemset create u
    $ rvm gemset use u
    # Install Rails 3
    $ gem install rails
    # Create new Rails application
    $ rails new u
    # Create .rvmrc for RVM to know which Ruby & gemset to use
    $ echo 'rvm use 1.9.2@u' > u/.rvmrc
    # Go into our project folder
    $ cd u
    # Initialize our SQLite3 DBs
    $ rake db:migrate
    $ rake db:migrate RAILS_ENV=test

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>

!SLIDE code incremental transition=uncover
## Your Bundler Gemfile ##

Setup our Gemfile to add our testing gems

    @@@Ruby
    # u/Gemfile
    source 'http://rubygems.org'

    gem 'rails', '3.0.7'
    gem 'sqlite3'

    # Bundle gems for the local environment
    group :development, :test do
      gem 'capybara'              # Ruby web browser / parser
      gem 'cucumber-rails'        # Cucumber for BDD testing
      gem 'database_cleaner'      # Cleans your DB between tests
      gem 'factory_girl_rails'    # Factories > Fixtures (opinion)
      gem 'rspec-rails', '~> 2.4' # RSpec for unit tests
    end

Install all your gems in one command:

    @@@sh
    $ bundle install

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>
