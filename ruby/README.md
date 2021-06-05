Create a Dockerfile in your Ruby app project
```
FROM ruby:2.5

# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

WORKDIR /usr/src/app

COPY Gemfile Gemfile.lock ./
RUN bundle install

COPY . .

CMD ["./your-daemon-or-script.rb"]

```

Generate a Gemfile.lock
The above example Dockerfile expects a Gemfile.lock in your app directory. This docker run will help you generate one. Run it in the root of your app, next to the Gemfile:
```
$ docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app ruby:2.5 bundle install

```
Run a single Ruby script
For many simple, single file projects, you may find it inconvenient to write a complete Dockerfile. In such cases, you can run a Ruby script by using the Ruby Docker image directly:
```
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp ruby:2.5 ruby your-daemon-or-script.rb

```