This has come in handy more times than it should have.

## Configuration

To redirect all requests to example.com:

```
heroku config:add NEW_BASE_URL=http://example.com
```

To use an alternative HTTP status code set `REDIRECT_STATUS`. Defaults to 302.
```
heroku config:add REDIRECT_STATUS=301
```

## Deployment

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/puria/heroku-redirect)

If the old app that you're redirecting from isn't a Node app you'll need to change the [buildpack](https://devcenter.heroku.com/articles/buildpacks):

```
heroku buildpacks:set heroku/nodejs
```

You can then replace the app by pushing with `-f`:

```
git push heroku master -f
```

**NOTE:** If the above doesn't work you may need to delete and re-create your Heroku app before pushing an entirely new Git repository into it.
