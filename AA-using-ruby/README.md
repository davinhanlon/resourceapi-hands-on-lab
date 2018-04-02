# Using ruby to make web requests 

## Introduction
Now that we can see that the light bulbs work and before we start puppetizing writing a simple script to change the light bulbs

## Get ruby

## Installing gems

require 'json' helps us play with json
require 'uri' allows manipulation of urls
require 'faraday' talks http for us
require 'pry' allows us to debug

## A simple piece of code

```
require 'json'
require 'uri'
require 'faraday'
require 'pry'
connection = Faraday.new(:url => "http://192.168.0.2/api/jheDoeqKBKnlJuzoDiB5ZxNxJBYsMvzLT3ubMw8n", :ssl => { :verify => false })
binding.pry
response   = connection.put('lights/3/state', { "alert" => "lselect" }.to_json)
```

### Excuting that code
bundle exec ruby simple.rb

### Explaining the code

### What next further reading
API lookup and help
a proper crazy example with tasks to complete
