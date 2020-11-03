# Example of a Rails App with BuildPack

Install pack cli from https://buildpacks.io/docs/tools/pack/

Build the image
```
pack build rails_example
```

Setup the database
```
docker run -e DATABASE_URL=postgres://admin:admin@127.0.0.1/rails_example?pool=5 -e SECRET_KEY_BASE=example --net=host rails-example rake db:setup
```

Run it:
```
docker run -e DATABASE_URL=postgres://admin:admin@127.0.0.1/rails_example?pool=5 -e SECRET_KEY_BASE=example --net=host rails-example
```

You should be able to access to http://127.0.0.1:5000/posts

# License

This is free software, and may be redistributed under the terms specified in the [LICENSE](LICENSE) file.
