Wufoo API Docs
========

Here is the source for the new Wufoo API documentation. It's built using [Slate](https://github.com/tripit/slate/), a great tool for generating static HTML documentation from Markdown files.

Check out the [live view](https://wufoo.github.io/docs)

Getting Started with Slate
------------------------------

To build and deploy Slate, here's what you need to do:

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 1.9.3 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

 1. Clone this repo and switch into the new directory
 2. Install all dependencies: `bundle install`
 3. Start the test server: `bundle exec middleman server`

You can now see the docs at <http://localhost:4567>. Whoa! That was fast!

Now that Slate is all set up your machine, you'll probably want to learn more about [editing Slate markdown](https://github.com/tripit/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/tripit/slate/wiki/Deploying-Slate).

4. When you've commited your changes, and you're ready to publish, run: `rake publish`
5. To publish to a different remote: `bundle exec rake publish REMOTE_NAME=personal`

Other examples of Slate documentation
---------------------------------

* [Travis-CI's API docs](http://docs.travis-ci.com/api/)
* [Mozilla's localForage docs](http://mozilla.github.io/localForage/)
* [Mozilla Recroom](http://mozilla.github.io/recroom/)
* [ChaiOne Gameplan API docs](http://chaione.github.io/gameplanb2b/#introduction)
* [Drcaban's Build a Quine tutorial](http://drcabana.github.io/build-a-quine/#introduction)
* [PricePlow API docs](https://www.priceplow.com/api/documentation)
* [Emerging Threats API docs](http://apidocs.emergingthreats.net/)
* [Appium docs](http://appium.io/slate/en/master)
* [Golazon Developer](http://developer.golazon.com)
* [Dwolla API docs](https://docs.dwolla.com/)
* [RozpisyZapasu API docs](http://www.rozpisyzapasu.cz/dev/api/)
* [Codestar Framework Docs](http://codestarframework.com/documentation/)
* [Buddycloud API](http://buddycloud.com/api)
* [Crafty Clicks API](https://craftyclicks.co.uk/api/)
* [Paracel API Reference](http://paracel.io/docs/api_reference.html)
* [Switch Payments Documentation](http://switchpayments.com/docs/) & [API](http://switchpayments.com/developers/)
* [Coinbase API Reference](https://developers.coinbase.com/api)
* [Whispir.io API](https://whispir.github.io/api)
* [NASA API](https://data.nasa.gov/developer/external/planetary/)
* [CardPay API](https://developers.cardpay.com/)
* [IBM Cloudant](https://docs-testb.cloudant.com/content-review/_design/couchapp/index.html)
* [Bitrix basis components](http://bbc.bitrix.expert/)

Attribution
--------------------

Slate makes of several other projects, such as:

- [Middleman](https://github.com/middleman/middleman)
- [jquery.tocify.js](https://github.com/gfranko/jquery.tocify.js)
- [middleman-syntax](https://github.com/middleman/middleman-syntax)
- [middleman-gh-pages](https://github.com/neo/middleman-gh-pages)
- [Font Awesome](http://fortawesome.github.io/Font-Awesome/)
