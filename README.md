# rumors-site

[![Build Status](https://travis-ci.org/cofacts/rumors-site.svg?branch=master)](https://travis-ci.org/cofacts/rumors-site) [![Coverage Status](https://coveralls.io/repos/github/cofacts/rumors-site/badge.svg?branch=master)](https://coveralls.io/github/cofacts/rumors-site?branch=master)

Rumors list / creation UI, with server-side rendering.

## Configuration

For development, copy `.env.sample` to `.env` and make necessary changes.

For production via [rumors-deploy](http://github.com/cofacts/rumors-deploy), do setups in `docker-compose.yml`.

## Development

This project uses NodeJS 8+ and npm 5+.

``` bash
$ npm install
$ npm run dev # Then visit http://localhost:3000

# Before you pull request, please lint your code first
$ npm run lint
# fix eslint
$ npm run lint:fix
# run test
$ npm t
```

### styled-jsx syntax highlighting

See: https://github.com/zeit/styled-jsx#syntax-highlighting

### Landing Page (Makeshift)

We build a temporary landing page in the repo [grants-landing-template](github.com/cofacts/grants-landing-template).

When the landing page repo is in the same directory of this repo, run the command below to update the landing page in this repo:

``` bash
grants-landing-template $ npm start
# After the landing page is compiled, ctrl-c

grants-landing-template $ cd ../rumors-site

rumors-site $ npm run landing
```

## Deploy

Build docker image. These images are the same, just tagged differently.

``` bash
# Production build
$ npm run build

# Staging build
$ npm run build:staging
```

Run the docker image on local machine, then visit `http://localhost:3000`.

``` bash
$ docker run --rm -p 3000:3000 -e "PORT=3000" mrorz/rumors-site
```

Push to dockerhub
``` bash
# Production
$ docker push mrorz/rumors-site:latest

# Staging
$ docker push mrorz/rumors-site:staging
```

## Design and Mockups

* [真的假的 hackfoldr](http://beta.hackfoldr.org/rumors)
* [網站 UI flow](https://i.imgur.com/lxas2Ic.jpg)
