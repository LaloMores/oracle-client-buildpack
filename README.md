# What's this

A quick && dirty fork of https://github.com/featurist/oracle-client-buildpack as the Oracle server I need to connect with
seems to be very old, I just need an older version of the oracle instant client lib.

This will install Oracle Client libraries (11.2.0.4).

# Description

Buildpack adds Oracle Client libraries (11.2.0.4).

It is intended to be used in conjunction with other buildpacks (e.g. node) for apps that require Oracle db connection.

## Usage

Either add `https://github.com/LaloMores/oracle-client-buildpack` to `.buildpacks` or set `BUILDPACK_URL=https://github.com/LaloMores/oracle-client-buildpack`

> You also need API buildpack, preceding this one. And an `Aptfile` in the root of your app containing:

I didn't understand the first sentence in this comment at first. From a different buildpack, I got that I needed to add an extra buildpack.

I added this one:

https://github.com/heroku/heroku-buildpack-apt.git (at index 1)

Then added the file `Aptfile` in the root my source with this content:

```
libaio1
```

## Testing

_Edit_: Not sure if this works.

### Setup

```
heroku create --buildpack https://github.com/heroku/heroku-buildpack-testrunner
```

### Run

```
git push heroku master
heroku run tests
```

## \*They're Hiring!

Featurist provides full stack, feature driven development teams. Want to join then? Check out [our career opportunities](https://www.featurist.co.uk/careers/).
