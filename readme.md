# Heroku Buildpack for Logstash

This buildpack downloads and installs Logstash into a Heroku app slug. It is a fork of [omc/heroku-buildpack-kibana](https://github.com/omc/heroku-buildpack-kibana).

## Usage

As a standalone buildpack:

    # Create a new project with the --buildpack option
    $ heroku create --buildpack https://github.com/Aluxian/heroku-buildpack-logstash

    # ...Or update an existing project with heroku buildpacks:set
    $ heroku buildpacks:set https://github.com/Aluxian/heroku-buildpack-logstash

    # Let the buildpack know where to find Logstash
    $ heroku config:set DOWNLOAD_URL="https://download.elastic.co/logstash/logstash/logstash-2.3.1.tar.gz"

    # Let Logstash know where to find Elasticsearch
    $ heroku config:set ELASTICSEARCH_URL="https://logstashuser:logstashpass@host.region.bonsai.io"

    # Create a Procfile to run the Logstash web server
    $ cat Procfileg
    web: logstash agent -f logstash.conf

    # Create a logstash.conf
    $ ...

    # Push the above to trigger a deploy
    $ git push heroku master

    # Verify and profit!
    $ heroku open
