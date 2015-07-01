---
layout:     post
title:      How to Setup Rspec Instead of Test::Unit in Rails
date:       2015-05-27 12:00:00
summary:    How can I use Rspec in my Rails unit tests?
categories: Rails
---

For a new project, you can setup the Rspec test suite in three steps.

First, generate the project without Test::Unit (which is what the `-T` is):

    rails new new_project_name -T

Next, make sure you have Rspec in your Gemfile:

    ...
    group :development, :test do
      ...
      gem 'rspec-rails'
    end

Finally, use the Rails installer to generate the specs:

    rails g rspec:install

To check that this worked, you should see a `spec` directory instead of `test` from the project root:

    ls new_project_name/spec

Don't forget to prepare the db for testing after you run any new migrations:

    rake db:test:prepare

Check out the [Rspec docs](https://relishapp.com/rspec/rspec-rails/docs/gettingstarted) for more details.




