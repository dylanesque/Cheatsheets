# Why Rails?

- Extremely battle-tested
- A flexible full-stack framework


# Installation

- Varies wildly depending on OS, see [here](http://installrails.com/)

# The Rails CLI

- [Offical docs](https://guides.rubyonrails.org/command_line.html)

- `rails server` or `rails s`
- `rails console` or `rails c`
- `rails generate` or `rails g`
- `rails test` or `rails t`
- `bundle install` or `bundle`

- `rails generate` can be undone by `rails destroy`, for example:

`rails generate model User name:string email:string`

`rails destroy model User`


# Creating a new application

1. Run `rails new <app_name>`
2. cd into application folder, and run `bundle install`
3. Run `rails server` to see the application in action.

- Add `gem 'rexml', '~> 3.2', '>= 3.2.4'` to Gemfile for testing.

- [Webpacker](https://github.com/rails/webpacker) is the standard in how Rails utilizes and builds the front-end in JS. This gets installed by default in Rails 6+ applications.

+ New Rails applications will automatically initialize a new Git repo

+ Adding the `-d=postgresql` flag to the above command uses PostgreSQL as the database.

+ The vast majority of code in a Rails project is in the `app` folder, including the models, views, and controllers.

+ THe routes.rb file is where most routing logic goes.

+ Routing to a root looks like this: `root '<controller_name>#<action_name>'`

+ The DB must be created using the `rake db:create:all` command

+ `rails db:migrate` populates database specs, while `rails db:rollback` empties them


+ You can seed a Rails db by filling the seeds.rb file with data, then using the command 'rails db:seed'

# Scaffolding

- `rails generate scaffold <Resource> <attribute:type>`

# Models

- ActiveRecord is the utility that Rails uses to interact with the database.

- Migrations exist to accomodate incremental changes to the database.

- The rails console is a good place to experiment with new database entities, making sure that you are getting vaild results when creating new instances of them, etc.



# Views 

- `application.html.erb` is a special layout file that Ruby provides

- The `provide/content_for` method adds variable content to the view:

`<% provide(:title, "Home") %>`

- ...and we can return that using Ruby's `yield`:

`<title><%= yield(:title) %></title>`



# Controllers


