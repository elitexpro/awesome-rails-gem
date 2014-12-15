# For Development

## User
[Devise](https://github.com/plataformatec/devise/) is a flexible authentication solution for Rails based on Warden. It:

* Is Rack based;
* Is a complete MVC solution based on Rails engines;
* Allows you to have multiple models signed in at the same time;
* Is based on a modularity concept: use only what you really need.

## Testing
[Capybara](https://github.com/jnicklas/capybara) helps you test web applications by simulating how a real user would interact with your app. 

[SimpleCov](https://github.com/colszowka/simplecov) is a code coverage analysis tool for Ruby

## Coding Style
[RuboCop](https://github.com/bbatsov/rubocop) is a Ruby static code analyzer. Out of the box it will enforce many of the guidelines outlined in the community [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide).

[Rails Best Practice](https://github.com/railsbp/rails_best_practices) is a code metric tool to check the quality of rails codes.

## Debug
[Better Errors](https://github.com/charliesome/better_errors) replaces the standard Rails error page with a much better and more useful error page.

If you would like to use Better Errors' advanced features (REPL, local/instance variable inspection, pretty stack frame names), you need to add the [binding_ _of__caller](https://github.com/banister/binding_of_caller).

## Excel
The [Spreadsheet](https://github.com/zdavatz/spreadsheet) Library is designed to read and write Spreadsheet Documents.

## Chart
[Chartkick](https://github.com/ankane/chartkick) help your to create beautiful Javascript charts with one line of Ruby.

## Integration with other services
[Slack Notifier](https://github.com/stevenosloan/slack-notifier) is a simple wrapper to send notifications to [Slack](https://slack.com/) webhooks.

## Environment Variables
[Figaro](https://github.com/laserlemon/figaro) is very simple, Heroku-friendly Rails app configuration using ENV and a single YAML file.

## Routing
[FriendlyId](https://github.com/norman/friendly_id) is the “Swiss Army bulldozer” of slugging and permalink plugins for ActiveRecord. It allows you to create pretty URL’s and work with human-friendly strings as if they were numeric ids for ActiveRecord models.

## Pagination
A Scope & Engine based, clean, powerful, customizable and sophisticated paginator for Rails 3 and 4
[https://github.com/amatsuda/kaminari/wiki](https://github.com/amatsuda/kaminari/wiki)

## API
[ActiveModel::Serializers](https://github.com/rails-api/active_model_serializers) brings convention over configuration to your JSON generation.

AMS does this through two components: serializers and adapters. Serializers describe which attributes and relationships should be serialized. Adapters describe how attributes and relationships should be serialized.

## Editor
The [redactor-rails](https://github.com/SammyLin/redactor-rails) is gem integrates the Redactor editor with the Rails 3.2 asset pipeline.

[redactor-rails(paperclip)](https://github.com/kausters/redactor-rails) is a redactor's paperclip no-devise edition with Bourbon/Compass support and unset editor styles

## Uploader
[Carrierwave](https://github.com/carrierwaveuploader/carrierwave) is a classier solution for file uploads for Rails, Sinatra and other Ruby web frameworks.

[MiniMagick](https://github.com/minimagick/minimagick) is a ruby wrapper for ImageMagick or GraphicsMagick command line.

[fog](https://github.com/fog/fog) is the Ruby cloud services library, top to bottom:

* Collections provide a simplified interface, making clouds easier to work with and switch between.
* Requests allow power users to get the most out of the features of each individual cloud.
* Mocks make testing and integrating a breeze.

## Record State Flow
[AASM](https://github.com/aasm/aasm) - State machines for Ruby classes (plain Ruby, Rails Active Record, Mongoid)

## View Helper
[Simple Form](https://github.com/plataformatec/simple_form) aims to be as flexible as possible while helping you with powerful components to create your forms. The basic goal of Simple Form is to not touch your way of defining the layout, letting you find the better design for your eyes.

## OAuth 
[omniauth-facebook](https://github.com/mkdynamic/omniauth-facebook)

[omniauth-google-oauth2](https://github.com/zquestz/omniauth-google-oauth2)

[omniauth-weibo-oauth2](https://github.com/beenhero/omniauth-weibo-oauth2)

[omniauth-twitter](https://github.com/arunagw/omniauth-twitter)

## Backend
The administration framework for Ruby on Rails applications. 
[http://activeadmin.info](http://activeadmin.info)

[active_skin](https://github.com/rstgroup/active_skin): Flat skin for active admin.

# For Production
## Errors

Use an error reporting service like [Rollbar](https://rollbar.com/).

Also, track 400 and 500 status codes.

```ruby
ActiveSupport::Notifications.subscribe "process_action.action_controller" do |name, start, finish, id, payload|
  if !payload[:status] or payload[:status].to_i >= 400
    # track it
  end
end
```

## Timeouts

Use [Slowpoke](https://github.com/ankane/slowpoke) for request and database timeouts.

```ruby
gem 'slowpoke'
```

## Throttling

Use [Rack Attack](https://github.com/kickstarter/rack-attack) to throttle and block requests.

## Slow Requests

Keep track of slow requests

```ruby
ActiveSupport::Notifications.subscribe "process_action.action_controller" do |name, start, finish, id, payload|
  duration = finish - start
  if duration > 5.seconds
    # track here
  end
end
```

## Unpermitted Parameters

```ruby
ActiveSupport::Notifications.subscribe "unpermitted_parameters.action_controller" do |name, start, finish, id, payload|
  # track here
end
```

## Audits & Version

[PaperTrail](https://github.com/airblade/paper_trail) lets you track changes to your models' data. It's good for auditing or versioning.

Soft delete: [paranoia](https://github.com/radar/paranoia)

## Failed Validations

```ruby
module TrackErrors
  extend ActiveSupport::Concern

  included do
    after_validation :track_errors
  end

  def track_errors
    if errors.any?
      # track here
    end
  end
end

ActiveRecord::Base.send(:include, TrackErrors)
```

## Failed CSRF

```ruby
class ApplicationController < ActionController::Base
  def handle_unverified_request_with_tracking(*args)
    # track here

    handle_unverified_request_without_tracking(*args)
  end
  alias_method_chain :handle_unverified_request, :tracking
end
```

## Logging

Use [Lograge](https://github.com/roidrage/lograge).

```ruby
gem 'lograge'
```

Add the following to `config/environments/production.rb`.

```ruby
config.lograge.enabled = true
config.lograge.custom_options = lambda do |event|
  options = event.payload.slice(:request_id, :user_id, :visit_id)
  options[:params] = event.payload[:params].except("controller", "action")
  # if you use Searchkick
  if event.payload[:searchkick_runtime].to_f > 0
    options[:search] = event.payload[:searchkick_runtime]
  end
  options
end
```

Add the following to `app/controllers/application_controller.rb`.

```ruby
def append_info_to_payload(payload)
  super
  payload[:request_id] = request.uuid
  payload[:user_id] = current_user.id if current_user
  payload[:visit_id] = ahoy.visit_id # if you use Ahoy
end
```
It attempt to bring sanity to Rails' noisy and unusable, unparsable and, in the context of running multiple processes and servers, unreadable default logging output

Instead of having an unparsable amount of logging output like this:

```
Started GET "/" for 127.0.0.1 at 2012-03-10 14:28:14 +0100
Processing by HomeController#index as HTML
  Rendered text template within layouts/application (0.0ms)
  Rendered layouts/_assets.html.erb (2.0ms)
  Rendered layouts/_top.html.erb (2.6ms)
  Rendered layouts/_about.html.erb (0.3ms)
  Rendered layouts/_google_analytics.html.erb (0.4ms)
Completed 200 OK in 79ms (Views: 78.8ms | ActiveRecord: 0.0ms)
```
you get a single line with all the important information, like this:
```
method=GET path=/jobs/833552.json format=json controller=jobs action=show status=200 duration=58.33 view=40.43 db=15.26
```

## Uptime Monitoring

Use an uptime monitoring service like [Pingdom](https://www.pingdom.com/) or [Uptime Robot](https://uptimerobot.com/).

Monitor web servers, background jobs, and scheduled tasks.

## Performance Monitoring

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

### Background Jobs and Rake Tasks

- jobs by type - total time, count
- errors

## Data Stores - Database, Elasticsearch, Redis
- requests by type - total time, count
- errors
- CPU usage
- space

### Redis
[redis-rb](https://github.com/redis/redis-rb) is a Ruby client that tries to match Redis' API one-to-one, while still providing an idiomatic interface. It features thread-safety, client-side sharding, pipelining, and an obsession for performance.

[redis-objects](https://github.com/nateware/redis-objects) provides a Rubyish interface to Redis, by mapping Redis data types to Ruby objects, via a thin layer over the redis gem. 


### External Services

- requests by type - total time, count
- errors

## Web Server

Use a high performance web server like [Unicorn](http://unicorn.bogomips.org/).

```ruby
gem 'unicorn'
```

## Security

Use SSL to protect your users. Add the following to `config/environments/production.rb`.

```ruby
config.force_ssl = true
```

## Development Bonus

[Fix double logging](https://github.com/rails/rails/issues/11415#issuecomment-57648388) in the Rails console. Create `config/initializers/log_once.rb` with:

```ruby
ActiveSupport::Logger.class_eval do
  def self.broadcast(logger)
    Module.new do
    end
  end
end
```

## Scheduled Jobs

[Whenever](https://github.com/javan/whenever) is a Ruby gem that provides a clear syntax for writing and deploying cron jobs. Example:
```ruby
every 3.hours do
  runner "MyModel.some_process"
  rake "my:rake:task"
  command "/usr/bin/my_great_command"
end
```

## TODO

- Redis timeout
- Elasticsearch timeout
- Background jobs
- Gemify parts

## Thanks

- [cant_wait gem](https://github.com/CarlosCD/cant_wait) for database timeouts
