[Codecov][1] Elixir Example
=======================

[![Build Status](https://travis-ci.org/codecov/example-elixir.svg?branch=master)](https://travis-ci.org/codecov/example-elixir) [![codecov](https://codecov.io/gh/codecov/example-elixir/branch/master/graph/badge.svg?token=)](https://codecov.io/gh/codecov/example-elixir)

This repository serves as an **example** on how to use [Codecov Global][4] for Elixir.

# Mix.exs

Add [excoveralls](https://hex.pm/packages/excoveralls) to your mix.exs deps.

# Circle CI

Add to your `.circleci/config.yml` file.
```yml
# Check https://circleci.com/docs/2.0/language-elixir/ for more details
version: 2.1
orbs:
  codecov: codecov/codecov@1.0.2

jobs:
  test:
    docker:
      - image: circleci/elixir:1.11.2
    steps:
      - checkout
      - run: mix do compile --warnings-as-errors, coveralls.json
      - codecov/upload:
        file: "./coveralls.json"
        token: "f0ab5451-efeb-4c8a-8f45-5f699c9db5ce"
```


View source and learn more about [Codecov Global Uploader][4]

We are happy to help if you have any questions. Please contact email our Support at [support@codecov.io](mailto:support@codecov.io)

[1]: https://codecov.io/
[4]: https://github.com/codecov/codecov-bash
