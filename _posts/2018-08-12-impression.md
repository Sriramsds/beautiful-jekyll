---
layout: post
title: Impressionist gem
date: 2018-08-12 17:44:00 +02:00
tags: ['rails','ruby','views','impressionist']
author: S.Muthukrthika
---
# Impressionist

A lightweight plugin that logs impressions per action or manually per model

## Why impressionist?

When you're a web developer many times a client will ask you to show a Views text somewhere.

For example, how many views does this Profile have? How many views does this Car listing have?

In Ruby on Rails, there's a very clean and simple Gem that allows you to quickly and correctly add this functionality to your website.

**Excited to add impressionist to your post , then follow these installation process**

## Installation
1. Add gem to your file
```ruby
gem 'impressionist'
```
2.Install with Bundler
```ruby
bundle install
```
3.Generate the impressions table migration
```ruby
rails g impressionist
```
4.Run the migration
```ruby
rake db:migrate
```
5.The following fields are provided in the migration:
```ruby
t.string   "impressionable_type"  # model type: Widget
t.integer  "impressionable_id"    # model instance ID: @widget.id
t.integer  "user_id"              # automatically logs @current_user.id
t.string   "controller_name"      # logs the controller name
t.string   "action_name"          # logs the action_name
t.string   "view_name"            # TODO: log individual views (as well as partials and nested partials)
t.string   "request_hash"         # unique ID per request, in case you want to log multiple impressions and group them
t.string   "session_hash"         # logs the rails session
t.string   "ip_address"           # request.remote_ip
t.text     "params"               # request.params, except action name, controller name and resource id
t.string   "referrer"             # request.referer
t.string   "message"              # custom message you can add
t.datetime "created_at"           # I am not sure what this is.... Any clue?
t.datetime "updated_at"           # never seen this one before either....  Your guess is as good as mine?? ;-)
```
## Usage
1.Log all actions in a controller
```ruby
WidgetsController < ApplicationController
   impressionist
 end
 ```
 2.Specify actions you want logged in a controller
 ```ruby
 WidgetsController < ApplicationController
   impressionist :actions=>[:show,:index]
 end
 ```
 3.Make your models impressionable. This allows you to attach impressions to an AR model instance. Impressionist will automatically log the Model name (based on action_name) and the id (based on params[:id]), but in order to get the count of impressions (example: @widget.impression_count), you will need to make your model impressionable
 ```ruby
 class Widget < ActiveRecord::Base
   is_impressionable
 end
 ```
 ** After this the basic impressionist gem will start to work on , and on refreshing your page everytime the views counter gets increased and gets viewed by the users **



