# testrail [![Gem Version](https://badge.fury.io/rb/testrail.png)](http://badge.fury.io/rb/testrail) [![Travis Status](https://travis-ci.org/krobi64/testrail.png)](https://travis-ci.org/krobi64/testrail) [![Code Climate](https://codeclimate.com/github/krobi64/testrail.png)](https://codeclimate.com/github/krobi64/testrail) [![Gemnasium](https://gemnasium.com/krobi64/testrail.png)](https://gemnasium.com/krobi64/testrail)

A Ruby client that tries to match TestRail's API one-to-one, while still
providing an idiomatic interface.

## Installation
    gem install testrail

or in Gemfile

    gem "testrail"

## Configuration

By default, Testrail's configuration points to their hosted service. You can set your api_key in either of the following ways:

    Testrail.config.api_key = 'my_api_key'

    Testrail.configure do |c|
      c.api_key = 'my_api_key'
    end

Configuration options [defaults] include:
* server: the location of the TestRail application. ['https://example.testrail.com']
* api_path: the path on the server that provides the api. ['/index.php?/miniapi/']
* api_key: the api_key required to access the TestRail application. [nil]
* logger:  the logging instance to use for capturing log messages. [Logger.new]

## Usage

    client = Testrail::Client.new
    response = client.add_case(<section_id>, body: {
      title: "A New Test",
      priority_id: 4,
      references: 'url_to_issue_tracker'
    })
    
    test_id = response.payload if response.success
    error = response.error unless response.success

# ToDo

* Add Testrail specific objects to represent the Testrail domain.

# Contributing to testrail
 
* Check out the latest master to make sure the feature hasn't been implemented or the bug hasn't been fixed yet.
* Check out the issue tracker to make sure someone already hasn't requested it and/or contributed it.
* Fork the project.
* Start a feature/bugfix branch.
* Commit and push until you are happy with your contribution.
* Make sure to add tests for it. This is important so I don't break it in a future version unintentionally.
* Please try not to mess with the Rakefile, version, or history. If you want to have your own version, or is otherwise necessary, that is fine, but please isolate to its own commit so I can cherry-pick around it.

## Copyright

Copyright (c) 2012 Kristine Robison. See LICENSE.txt for
further details.

