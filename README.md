# Sheets api starter

This is a netlify starter to expose a Google Sheets worksheet as an API using Netlify serverless functions. It exposes the functions defined in https://github.com/gvdp/sheets-as-an-api.

## Deploy your own

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/gvdp/sheets-api-starter)

## Config

Update `src/config.ts` file with the ids and names of the sheets you want to expose. 

### Google Application

Create a Google application to be able to authenticate, set the `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` env vars.

<!-- todo: expand on this explanation -->

### Redis cache

There is an optional Redis cache to configura using `REDIS_KEY` and `REDIS_HOST`.

<!-- todo: expand on this explanation -->

## Deploy

When using the starter button, a new Netflify project is created, and the functions are automatically served. You need to set the env variable `REFRESH_TOKEN` to authenticate your Netlify functions with the Google Sheets api.

Call the root URL of the newly deployed functions, it will redirect to an authentication page. After allowing access, the function will give you a token, set this as an env variable manually, or run 

```
ntl env:set REFRESH_TOKEN *****
```

with the CLI. You're API is now authenticated.

## Local development

Use [Volta](https://volta.sh) to automatically configure your local Node and Pnpm versions.


Run `pnpm install` then `pnpm start`, functions are then served at `localhost:8888` by default.


## API

Entrypoint `http://localhost:8888/sheet` will list all configured sheets.

<!-- todo: list other endpoints -->
