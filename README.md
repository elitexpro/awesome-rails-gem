# Rails Gem List
A collection of rails gem we ever used in practice.

* [Rails Gem List](#rails-gem-list)
  * [User](#user)
  * [Active Record](#active-record)
  * [Plugins](#plugins)
  * [API](#api)
  * [File Upload](#file-upload)
  * [Search](#search)
  * [Scheduled/Recurrence Jobs](#scheduledrecurrence-jobs)
  * [View Helper](#view-helper)
  * [Environment Variables](#environment-variables)
  * [Admin Panel](#admin-panel)
  * [Logging](#logging)
  * [Debug](#debug)
  * [Coding Style](#coding-style)
  * [Testing](#testing)
  * [Production](#production)

## User
* [Devise](https://github.com/plataformatec/devise/) - Devise is a flexible authentication solution for Rails based on Warden. It:
* [Pundit](https://github.com/elabs/pundit) - Pundit provides a set of helpers which guide you in leveraging regular Ruby classes and object oriented design patterns to build a simple, robust and scaleable authorization system.
* OmniAuth
	* [omniauth-facebook](https://github.com/mkdynamic/omniauth-facebook)
	* [omniauth-google-oauth2](https://github.com/zquestz/omniauth-google-oauth2)
	* [omniauth-weibo-oauth2](https://github.com/beenhero/omniauth-weibo-oauth2)
	* [omniauth-twitter](https://github.com/arunagw/omniauth-twitter)

## Active Record
* [Enumerize](https://github.com/brainspec/enumerize) - Enumerated attributes with I18n and ActiveRecord/Mongoid support. It can be integrated with Simple Form.
* [counter_culture](https://github.com/magnusvk/counter_culture) - Turbo-charged counter caches for your Rails app. Huge improvements over the Rails standard counter caches.
* [Sequenced](https://github.com/djreimer/sequenced) - Sequenced is a simple gem that generates scoped sequential IDs for ActiveRecord models.
* [FriendlyId](https://github.com/norman/friendly_id) - FriendlyId is the “Swiss Army bulldozer” of slugging and permalink plugins for ActiveRecord. It allows you to create pretty URL’s and work with human-friendly strings as if they were numeric ids for ActiveRecord models.
* [AASM](https://github.com/aasm/aasm) - State machines for Ruby classes (plain Ruby, Rails Active Record, Mongoid)
* [PaperTrail](https://github.com/airblade/paper_trail) - PaperTrail lets you track changes to your models' data. It's good for auditing or versioning.
* [paranoia](https://github.com/radar/paranoia) - ActiveRecord plugin allowing you to hide and restore records without actually deleting them.
* [Validates](https://github.com/kaize/validates) - Validates provides collection of useful custom validators for Rails applications, including:
	* EmailValidator
	* UrlValidator
	* SlugValidator
	* MoneyValidator
	* IpValidator
	* AssociationLengthValidator
	* AbsolutePathValidator
	* UriComponentValidator
	* ColorValidator
	* EanValidator (EAN-8 & EAN-13)
* [globalize](https://github.com/globalize/globalize) - Rails I18n de-facto standard library for ActiveRecord model/data translation.
* [deep_cloneable](https://github.com/moiristo/deep_cloneable) - This gem gives every ActiveRecord::Base object the possibility to do a deep clone that includes user specified associations.
* [social_shares](https://github.com/Timrael/social_shares) - Check how many times url was shared in social networks.
* [public_activity](https://github.com/chaps-io/public_activity) - Easy activity tracking for models - similar to Github's Public Activity
* Tagging
	* [ActsAsTaggableOn](https://github.com/mbleigh/acts-as-taggable-on) - A tagging plugin for Rails applications that allows for custom tagging along dynamic contexts.
	* [closure_tree](https://github.com/mceachen/closure_tree) - Easily and efficiently make your ActiveRecord models support hierarchies.

## Plugins
* [Spreadsheet](https://github.com/zdavatz/spreadsheet) - Library is designed to read and write Spreadsheet Documents.
* [Chartkick](https://github.com/ankane/chartkick) - Chartkick helps your to create beautiful Javascript charts with one line of Ruby.
* [kaminari](https://github.com/amatsuda/kaminari) - A Scope & Engine based, clean, powerful, customizable and sophisticated paginator for Rails 3 and 4.
* [CKEditor](https://github.com/galetahub/ckeditor) - CKEditor is a WYSIWYG text editor designed to simplify web content creation. It brings common word processing features directly to your web pages. Enhance your website experience with our community maintained editor. [ckeditor.com](http://ckeditor.com)
* [HTML::Pipeline](https://github.com/jch/html-pipeline) - GitHub HTML processing filters and utilities. This module includes a small framework for defining DOM based content filters and applying them to user provided content.
* [Slack Notifier](https://github.com/stevenosloan/slack-notifier) is a simple wrapper to send notifications to [Slack](https://slack.com/) webhooks.

## API
* [ActiveModel::Serializers](https://github.com/rails-api/active_model_serializers) - Serializer brings convention over configuration to your JSON generation.
* [Jbuilder](https://github.com/rails/jbuilder) - Jbuilder gives you a simple DSL for declaring JSON structures that beats massaging giant hash structures. This is particularly helpful when the generation process is fraught with conditionals and loops.
* [rest-client](https://github.com/rest-client/rest-client) - Simple HTTP and REST client for Ruby, inspired by microframework syntax for specifying actions.
* [has_scope](https://github.com/plataformatec/has_scope) - Map incoming controller parameters to named scopes in your resources.

## File Upload
* [Carrierwave](https://github.com/carrierwaveuploader/carrierwave) - Carrierwave is a classier solution for file uploads for Rails, Sinatra and other Ruby web frameworks.
  * [carrierwave_backgrounder](https://github.com/lardawge/carrierwave_backgrounder) - Offload CarrierWave's image processing and storage to a background process using Delayed Job, Resque, Sidekiq, Qu, Queue Classic or Girl Friday.
  * [CarrierWave Crop](https://github.com/kirtithorat/carrierwave-crop/) - Carrierwave extension to crop uploaded images using Jcrop plugin with preview.
* [remotipart](https://github.com/JangoSteve/remotipart) - Rails jQuery file uploads via standard Rails "remote: true" forms.
* [MiniMagick](https://github.com/minimagick/minimagick) - MiniMagick is a ruby wrapper for ImageMagick or GraphicsMagick command line.
* [fog](https://github.com/fog/fog) - Fog is the Ruby cloud services library, top to bottom.

## Search
* [ransack](https://github.com/activerecord-hackery/ransack) - Ransack enables the creation of both simple and advanced search forms for your Ruby on Rails application
* [elasticsearch-rails](https://github.com/elasticsearch/elasticsearch-rails) - Elasticsearch integrations for ActiveModel/Record and Ruby on Rails.
* [Chewy](https://github.com/toptal/chewy) - High-level Elasticsearch Ruby framework based on the official elasticsearch-ruby client.
* [Chewy_Kiqqer](https://github.com/averell23/chewy_kiqqer) - This is an alternative udpate/callback mechanism for Chewy. It queues the updates as Sidekiq jobs.

## Scheduled/Recurrence Jobs
* [Whenever](https://github.com/javan/whenever) - Whenever is a Ruby gem that provides a clear syntax for writing and deploying cron jobs.
* [Sidekiq](https://github.com/mperham/sidekiq) - Simple, efficient background processing for Ruby.
	* [sidetiq](https://github.com/tobiassvn/sidetiq) - Recurring jobs for sidekiq
* [Sucker Punch](https://github.com/brandonhilkert/sucker_punch) - Sucker punch is a single-process Ruby asynchronous processing library.

## View Helper
* [Simple Form](https://github.com/plataformatec/simple_form) - Simple form aims to be as flexible as possible while helping you with powerful components to create your forms. The basic goal of Simple Form is to not touch your way of defining the layout, letting you find the better design for your eyes.
* [Nested Form](https://github.com/ryanb/nested_form) - This is a Rails gem for conveniently manage multiple nested models in a single form. It does so in an unobtrusive way through jQuery or Prototype. It can also be integrated with Simple Form.
* [meta-tags](https://github.com/kpumuk/meta-tags) - Search Engine Optimization (SEO) plugin for Ruby on Rails applications.
* [active_link_to](https://github.com/comfy/active_link_to) - active_link_to adds css 'active' class to your links.

## Environment Variables
* [Figaro](https://github.com/laserlemon/figaro) - Figaro is very simple, Heroku-friendly Rails app configuration using ENV and a single YAML file.
* [dotenv](https://github.com/bkeepers/dotenv) - Dotenv is a gem that allows you to set your environment variables in .env file, and it will load it in to ENV.
* [opsworks-dotenv](https://github.com/mikamai/opsworks-dotenv) - Opsworks-dotenv let you configure the environment for you Rails application using OpsWorks, Chef and Dotenv

## Admin Panel
* [ActiveAdmin](http://activeadmin.info) - ActiveAdmin is a administration framework for Ruby on Rails applications. 
	- [active_skin](https://github.com/rstgroup/active_skin): Flat skin for active admin.
* [RailsAdmin](https://github.com/sferik/rails_admin) - RailsAdmin is a Rails engine that provides an easy-to-use interface for managing your data.

## Logging
* [Impressionist](https://github.com/charlotte-ruby/impressionist) - Impressionist can log page impressions (technically action impressions), but it is not limited to that. You can log impressions multiple times per request. And you can also attach it to a model. The goal of this project is to provide customizable stats that are immediately accessible in your application as opposed to using Google Analytics and pulling data using their API. 
* [Ahoy](https://github.com/ankane/ahoy) - Ahoy provides a solid foundation to track visits and events in Ruby, JavaScript, and native apps.
* [Lograge](https://github.com/roidrage/lograge) - An attempt to tame Rails' default policy to log everything.

## Debug
* [Better Errors](https://github.com/charliesome/better_errors) - Better errors replaces the standard Rails error page with a much better and more useful error page.
	* If you would like to use Better Errors' advanced features (REPL, local/instance variable inspection, pretty stack frame names), you need to add the [binding_ _of__caller](https://github.com/banister/binding_of_caller).
* [RailsPanel](https://github.com/dejan/rails_panel) - RailsPanel is a Chrome extension for Rails development that will end your tailing of development.log. 

## Coding Style
* [RuboCop](https://github.com/bbatsov/rubocop) - Rubocop is a Ruby static code analyzer. Out of the box it will enforce many of the guidelines outlined in the community [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide).
* [Rails Best Practice](https://github.com/railsbp/rails_best_practices) - Rails best practice is a code metric tool to check the quality of rails codes.

## Testing
* [rspec-rails](https://github.com/rspec/rspec-rails) - Rspec-rails is a testing framework for Rails 3.x and 4.x.
* [Capybara](https://github.com/jnicklas/capybara) - Capybara helps you test web applications by simulating how a real user would interact with your app. And drivers:
  - [capybara-webkit](https://github.com/thoughtbot/capybara-webkit) - Capybara-webkit is a capybara driver that uses Webkit via QtWebkit.
  - [selenium-webdriver](https://github.com/vertis/selenium-webdriver) - Selenium-webdriver provides ruby bindings for WebDriver.
  - [poltergeist](https://github.com/teampoltergeist/poltergeist) - Poltergeist allows you to run your Capybara tests on a headless WebKit browser, provided by PhantomJS.
* [factory_girl](https://github.com/thoughtbot/factory_girl) - Factory_girl is a fixtures replacement with a straightforward definition syntax, support for multiple build strategies (saved instances, unsaved instances, attribute hashes, and stubbed objects), and support for multiple factories for the same class (user, admin_user, and so on), including factory inheritance.
* [factory_girl_rails](https://github.com/thoughtbot/factory_girl_rails) - Factory_girl_rails provides Rails integration for factory_girl.
* [Database Cleaner](https://github.com/DatabaseCleaner/database_cleaner) - Database Cleaner is a set of strategies for cleaning your database in Ruby.Support ActiveRecord, DataMapper, Sequel, MongoMapper, Mongoid, CouchPotato, Ohm and Redis.
* [shoulda-matchers](https://github.com/thoughtbot/shoulda-matchers) - Shoulda-matchers provides serveral matchers for testing common Rails functionality.
* [ResponseCodeMatchers](https://github.com/r7kamura/response_code_matchers) - ResponseCodeMatchers provides rspec matchers to match http response code.
* [SimpleCov](https://github.com/colszowka/simplecov) - SimpleCov is a code coverage analysis tool for Ruby

## Production
* [Rollbar](https://github.com/rollbar/rollbar-gem) - Exception tracking and logging from Ruby to Rollbar.
* [Slowpoke](https://github.com/ankane/slowpoke) - Rack::Timeout is great. Slowpoke makes it better.
* [Rack Attack](https://github.com/kickstarter/rack-attack) - Rack middleware to blocking & throttling.
* [Responders](https://github.com/plataformatec/responders) - A set of Rails responders to dry up your application.

### Uptime Monitoring

Use an uptime monitoring service like [Pingdom](https://www.pingdom.com/) or [Uptime Robot](https://uptimerobot.com/).

Monitor web servers, background jobs, and scheduled tasks.

### Performance Monitoring

Use a performance monitoring service like [New Relic](http://newrelic.com/), [AppSignal](https://appsignal.com/) or [Skylight](https://www.skylight.io).

Be sure to monitor:

### Web Requests

- requests by action - total time, count
- errors - with affected users
- queue time - `X-Request-Start` header
- timeouts
- 404s
- invalid authenticity token
- unpermitted parameters
- invalid form submissions

### Web Server

Use a high performance web server like [Unicorn](http://unicorn.bogomips.org/).

```ruby
gem 'unicorn'
```

One thing we thought Unicorn missed, is killing the Unicorn workers based on the number of requests and consumed memories.

[unicorn-worker-killer](https://github.com/kzk/unicorn-worker-killer) gem provides automatic restart of Unicorn workers based on 1) max number of requests, and 2) process memory size (RSS), without affecting any requests.

Add these lines to your `config.ru`.

```ruby
# Unicorn self-process killer
require 'unicorn/worker_killer'

# Max requests per worker
use Unicorn::WorkerKiller::MaxRequests, 3072, 4096

# Max memory size (RSS) per worker
use Unicorn::WorkerKiller::Oom, (192*(1024**2)), (256*(1024**2))
```

### Security

Use SSL to protect your users. Add the following to `config/environments/production.rb`.

```ruby
config.force_ssl = true
```
