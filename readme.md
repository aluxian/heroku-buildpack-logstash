Heroku buildpack: Kibana
========================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that runs a [kibana](https://www.elastic.co/downloads/kibana) server.

Usage
-----

    $ cat .buildpacks
    https://github.com/issueapp/heroku-buildpack-kibana

    # for new project
    $ heroku create --buildpack https://github.com/issueapp/heroku-buildpack-kibana

    # for existing project
    $ heroku buildpacks:set https://github.com/issueapp/heroku-buildpack-kibana

    $ heroku config:set ELASTICSEARCH_URL="https://user:pass@elastic.cluster.com:9200"
    $ heroku config:set DOWNLOAD_URL="https://download.elastic.co/kibana/kibana/kibana-4.1.0-linux-x64.tar.gz"

    $ git push heroku master

    # verify and profit!
    $ heroku open
