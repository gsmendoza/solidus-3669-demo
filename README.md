# README

This is a demo for https://github.com/solidusio/solidus/pull/3715.

## Manual testing

```cucumber
Given my local solidus repo is checked out to https://github.com/solidusio/solidus/pull/3715

And I have https://github.com/gsmendoza/solidus-3669-demo cloned to a directory
  in the same directory as solidus

When I set `Spree::Api::Config[:disable_api_routes]` to true in `config/initializers/spree.rb`
And I run `rails routes`
Then I should not see any of the `Spree::Core::Engine` api routes
And I should continue seeing the `Spree::Core::Engine` backend routes

When I set `Spree::Api::Config[:disable_api_routes]` to false in `config/initializers/spree.rb`
And I run `rails routes`
Then I should see the `Spree::Core::Engine` api routes
And I should see the `Spree::Core::Engine` backend routes
```
