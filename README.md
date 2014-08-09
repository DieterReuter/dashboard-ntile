Check out http://shopify.github.com/dashing for more information.


# Example Dashboard based on `Ntile Widget`

See https://github.com/PareidoliaX/ntile_widget

A widget for Shopify's Dashing gem that shows numbers in statistical context.


## Steps to create this example
1. include deps into your `Gemfile`
```ruby
gem 'faker'
gem 'activesupport'
```
2. install the Ntile Widget from a Gist
```bash
dashing install 6757706
bundle install
```
3. install the example Dashboard, and replace `exsales.erb`
```bash
dashing g dashboard Exsales
cd dashboards
curl -OL https://raw.githubusercontent.com/PareidoliaX/ntile_widget/master/dashboards/exsales.erb
```
4. maybe cleanup all unused files


## Start the Ntile Dashboard server
```bash
bundle install
dashing start
```
On your host machine just start your web browser
```bash
open http://127.0.0.1:3030/
```
And you'll see the new sample dashboard up and running.
![Screenshot-Dashboard](/images/screenshot-dashboard.jpg)


# Licensing
Copyright (c) 2014 Dieter Reuter

MIT License, see LICENSE.txt for more details.
