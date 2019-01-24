# ttgint/fluentd-es

This repo contains 

- a fluentd image configured with elasticsearch output plugin
- a compose file and environment for setting up a containerized logging infrastructure

## Setup

`docker-compose up`

## Logging

### From containers

Use fluentd driver to forward console output

`docker run --log-driver=fluentd --log-opt fluentd-address=localhost:24224 hello-world`

### From other environments

Use `fluent-cat` to forward console output

`echo '{"message":"hello"}' | fluent-cat debug.log`

## Acknowledgments
Based on [this article](https://docs.fluentd.org/v0.12/articles/docker-logging-efk-compose)