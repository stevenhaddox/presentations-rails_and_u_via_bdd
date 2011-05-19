<!SLIDE code transition=zoom>
## Initialize Test Suite ##

Setup our test suite with a few simple commands:

    @@@sh
    # Setup Cucumber
    $ rails generate cucumber:install
    # Setup RSpec
    $ rails generate rspec:install

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>

<!SLIDE code transition=uncover>
## Cucumber Feature ##

The very first thing a visitor does is load the homepage:

    @@@Ruby
    #u/features/load_the_homepage.feature
    Feature: Visitor comes to the site

      As a visitor
      I want to find out about the site through different pages
      In order to decide if I'll shorten a URL. 

      Scenario: Load the homepage
        Given I am on the homepage
        Then I should see "Welcome to 'u'"
        And I should see "Short for uRL Shortener"

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>

<!SLIDE center transition=uncover>
### Run the scenario ###

<img src="cuke-fail-1.png" style="width:900px; height:650px;">

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>

<!SLIDE small transition=uncover>
# FAIL #

Why did it fail? I thought this was supposed to be easy?!

Failing early is good, but it looks like there's already content on the homepage when it tried to scan for the text we expected.  Let's investigate it by loading the application ourselves & see what's there.

    @@@sh
    $ rails s

Then navigate to: http://localhost:3000
<img src="homepage_fail.png" style="width:640px; height:452px;">

<div class="footer">
  <p>Facilitated by: Booz, Allen, Hamilton | Presented by: <a href="http://twitter.com/stevenhaddox">@stevenhaddox</a></p>
</div>
