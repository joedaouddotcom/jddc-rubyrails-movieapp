# jddc-rubyrails-movieapp
Ruby on Rails app which allows you to view movies and actor information from a database

## Some notes on my journey

#Ruby Notes

## Create a new app
rails new [APP NAME]

## Install the Gems
bundle install

## Create models and Controllers
rails generate model [MODEL NAME]
rails generate controller [CONTROLLER NAME]

## Add Methods
Inside the .rb files (typically located in /models/) you can add methods within Classes
ex:
has_many :[.rb file you are referring to]
has_many through: :[.rb file you are referring to]
belongs_to :[.rb file you are referring to]

## Database Stuff
Database has different table files which are also .rb and are named with a timestamp and the model name

To create string columns inside of the database:
t.string :[STRING_NAME]

To create foreign keys that point to other tables in other databases:
t.belongs_to :[db name], index: true

To run the migration and update the database cmd:
rake db:migrate

To seed the database with data (you must have a seeds.rb file with data to seed):
rake db:seed

## Routes
These are configured in routes.rb usually located in the /config/ folder

To create new routes that map URLs to an index action:
get '/[FOLDER NAME]' => 'FOLDER NAME#index'

To add the index action to display in your controller within the Class:
    def index
        @[CONTROLLER] = CONTROLLER.all
    end

Add a route to display a specific page/id in the ROUTES file:
get '/tags/:id' => 'tags#show', as: :tag

## Add content to pages
Usually you want to iterate through the data in the controller with a for loop.

Example for loop:
    //Grabs the movies
    <% @movies.each do |movie| %>
    <div class="movie">
    //Shows an image, title and year for all movies in the DB
      <%= image_tag movie.image %>
      <h3><%= movie.title %></h3>
      <p><%= movie.release_year %></p>
    </div>
    <% end %>



