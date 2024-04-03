# dockerize_rails_app

## Generate Rails App with Docker Image

### Rails Image

#### Dockerfile.rails

```
# Dockerfile.rails
FROM ruby:3.1.2 AS rails-toolbox

# Default directory
ENV INSTALL_PATH /opt/app
RUN mkdir -p $INSTALL_PATH

# Install rails
RUN gem install rails bundler
#RUN chown -R user:user /opt/app
WORKDIR /opt/app

# Run a shell
CMD ["/bin/sh"]
```

And, build the image:

```docker build -t rails-toolbox -f Dockerfile.rails .```


