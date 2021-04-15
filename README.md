# What's this

A quick && dirty fork of https://github.com/featurist/oracle-client-buildpack as the Oracle server I need to connect with
seems to be very old, I just need an older version of the oracle instant client lib.

This will install Oracle Client libraries (11.2.0.4).

# Description

Buildpack adds Oracle Client libraries (11.2.0.4).

It is intended to be used in conjunction with other buildpacks (e.g. node) for apps that require Oracle db connection.

## Usage

1. Dependency buildpack

Add the libaio buildpack first in order to provide libaio1:

```
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-apt.git --index 1
```

Then add a file named `Aptfile` in the root of your source code with this content:

```
libaio1
```


2. Add this buildpack

```
heroku buildpacks:add https://github.com/LaloMores/oracle-client-buildpack --index 2
```

Alternatively, use `.buildpacks` to add both buildpacks in order.

## Testing

_Edit_: Not sure if this works.
