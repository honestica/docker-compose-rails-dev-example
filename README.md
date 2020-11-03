# Example of a Rails App with Docker Compose for development

This is an example of how I use [Docker](https://docs.docker.com/) and
[Docker Compose](https://docs.docker.com/compose/) to develop my rails apps.

It is an ideal project setup for new and experienced developers alike, and allows
to a nearly trouble-free environment setup in their development machines.

In this example we'll fire up a full app environment consisting of the following:

 - A [postgres container](https://github.com/vovimayhem/docker-compose-rails-dev-example/blob/master/docker-compose.yml#L17)
 which hosts the app's database.
 - A [redis container](https://github.com/vovimayhem/docker-compose-rails-dev-example/blob/master/docker-compose.yml#L38)
 which hosts the app's job queue.
 - An example Rails app running 3 processes on separate containers:
   - A [`jobs` container](https://github.com/vovimayhem/docker-compose-rails-dev-example/blob/master/docker-compose.yml#L51)
   running the app's job processor ([Sidekiq](http://sidekiq.org/)).
   - A [`worker` container](https://github.com/vovimayhem/docker-compose-rails-dev-example/blob/master/docker-compose.yml#L105)
   running the Rails web server.
   - A [`test` container](https://github.com/vovimayhem/docker-compose-rails-dev-example/blob/master/docker-compose.yml#L113)
   running [guard](http://guardgem.org/), which fires tests automatically whenever a change in the
   app code is detected.

You'll need to follow some instructions to get this example running:

# License

This is free software, and may be redistributed under the terms specified in the [LICENSE](LICENSE) file.
