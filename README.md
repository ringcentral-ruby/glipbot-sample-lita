Glipbot Sample Using Lita
=========================

This project contains an example Glipbot using [RingCentral](https://ringcentral.com)'s Glip API for the Glip collaboration service (https://glip.com).

## Prerequisites

* Basic awareness of [Lita](https://www.lita.io/)
* Access to an active RingCentral Glip Account with access to the [Developer Portal](https://developers.ringcentral.com)
* Ruby version 2.2.2 or greater

## Installation

### Heroku Setup

If you already have your RingCentral API Keys and Glip account created and available, you can use [Heroku One-Button Deployment](https://devcenter.heroku.com/articles/heroku-button).

Notes:

1. **REMEMBER, you must have all the prerequisites to configure the app properly**
2. The demo defaults to paid Heroku `Hobby` and `redistogo:micro` tiers. This can be changed to free tiers by forking the repo and updating [`app.json`](app.json) to set the tiers to `Free` and `redistogo.nano`.
3. Zendesk usage is optional and you can leave the default values in place if you do not have a Zendesk account

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

The settings are located in the [`app.json`](app.json) file. If you wish to change any settings such as the Dyno type or [Redis To Go](https://elements.heroku.com/addons/redistogo) plan, please fork the repo and deploy from your fork.

### Manual Setup

For a manual set up, perform the following steps:

1. install and run Redis, e.g. using `$ redis-server`
2. clone the repo
3. create the `.env` file and run `lita` as follows:

```bash
$ git clone https://github.com/ringcentral-ruby/glipbot-sample-lita
$ cd glipbot-sample-lita
$ cp .env.tmpl .env
$ vi .env
$ bundle install
$ lita
```

Information on installing Redis is available on the [Lita User Guide under Manual Installation](https://docs.lita.io/getting-started/installation/#manual-installation).

## Usage

### Quickstart

After starting the service, text the following [`lita-inspirebot`][repo-lita-inspirebot-link] interactions to your configured Glip account:

1. `quote authors`
2. `quote jobs`
3. `@lita 8ball`

### Handlers Information

This demo apps loads 3 handlers:

Lita configuration is loaded in [lita_config.rb](lita_config.rb) and [lita_dotenv](.lita_dotenv) enables loading of many configuration types via the environment variables depending upon if you're using `.env` to load environment variables or if you are using Heroku environment variables.

By default, this example includes the following handlers:

| Handler | Sample command | Notes |
|---------|----------------|-------|
| [`lita-inspirebot`][repo-lita-inspirebot-link] | `quote jobs` | supports RingCentral sandbox accounts |
| [`lita-eightball`](https://github.com/webdestroya/lita-eightball) | `@lita 8ball` | requires Ringcentral production account |

#### Changing Handlers

To change the handlers that are loaded, edit the `Gemfile` as normal per [Lita](https://lita.io).

## Links

RingCentral Developer Program

* https://developers.ringcentral.com/

## Contributing

1. Fork it ( http://github.com/ringcentral-ruby/glipbot-sample-lita/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Glipbot Sample for Lita is available under the MIT-style license. See [LICENSE.txt](LICENSE.txt) for details.

Glipbot Sample for Lita &copy; 2017 by John Wang

 [repo-lita-inspirebot-link]: https://github.com/grokify/lita-inspirebot
