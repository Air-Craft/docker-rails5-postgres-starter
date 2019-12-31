## Instructions

Clone the repo, then run the following setup...
````
docker-compose build
docker-composer run web bundle install
(docker composer run web bundle update) # sometimes required to sort out dependency issues
docker-compose run web bundle exec rails db:setup
````

To launch the db & server
````
docker-compose up
````

To break down
````
docker-compose doan
````

Gems are volume mounted so no need to rebuild to bundle install. Just run
````
docker-composer run web bundle install
````

Note, they are NOT saved in the image itself. A seperate Dockerfile for production
is required which _should_ include the `bundle install` (and `db:setup`?) commands.
