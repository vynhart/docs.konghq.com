# KONG Website

This repository is the source code for [Kong](https://github.com/Kong/kong)'s website. It is a [Jekyll](http://jekyllrb.com/) website hosted on GitHub pages.

## Requirements

- [npm](https://www.npmjs.com/)
- [Bundler](http://bundler.io/)
- [Ruby](https://www.ruby-lang.org) (>= 2.0, < 2.3)
- [Python](https://www.python.org) (>= 2.7.X, < 3)

## Install

>
```bash
gem install bundler
npm install
```

## Running locally

>
```bash
npm start
```

## Deploying

This will deploy to GitHub pages:

>
```bash
npm run deploy
```

## Search

We are using Algolia [docsearch](https://www.algolia.com/docsearch) for our CE
documentation search. The algolia index is maintained by Algolia through their
docsearch service. Their [scraper](https://github.com/algolia/docsearch-scraper)
runs every 24 hours. The config used by the scraper is open source for
docs.konghq.com and can be found [here](https://github.com/algolia/docsearch-configs/blob/master/configs/getkong.json).
To update the scraper config, you can submit a pull request to the config. To
test a config change locally, you will need to run their open source
[scraper](https://github.com/algolia/docsearch-scraper) against your own
scraper to test out config changes.

## Generating the Plugin Development Kit documentation

- Have a local clone of Kong
- Install Luarocks (comes with Kong)
- Install `ldoc` using Luarocks: `luarocks install ldoc 1.4.6`
- In the Kong repository, checkout the desired branch/tag/release
- Run: `KONG_PATH=path/to/your/kong/folder KONG_VERSION=0.14.x gulp pdk-docs`
- This command will attempt to:
  * Obtain an updated list of modules from your local PDK and put it inside
    your nav file
  * Generate documentation for all the modules in your PDK (where possible) and
    put in a folder inside your version docs

## Listing Your Extension in the Kong Catalog

We encourage developers to list their Kong plugins and integrations (which
we refer to collectively as "extensions") in the
[Kong Catalog](https://docs.konghq.com/catalog), with documentation hosted
on the Kong website for ready access.

See CONTRIBUTING.md for more information.
