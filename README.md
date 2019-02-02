# Ext JS Employee Directory
Ext JS Sample Application - Employee Directory (Coworkee)

## Getting started
### Prerequisite
- Login to Sencha [NPM Repository](http://docs.sencha.com/extjs/6.7.0/guides/getting_started/open_tooling.html#getting_started-_-open_tooling_-_step_2__login_to_the_npm_repository)

`npm login --registry=https://npm.sencha.com --scope=@sencha`

### Install the server
Install the server node.js dependencies:

    $ cd server
    $ npm install

### Build the client
Install the Ext JS framework for the application:

    $ cd client
    $ npm install

IMPORTANT NOTE: If you face an issue during the build with being unable to resolve the dependency for "google", there might be an issue with the @sencha/ext-google npm package. One workaround that fixes this is copying this from "node_modules/@sencha" folder to packages/local inside the client folder. This allows the build to resolve the "google" requirement.

Development build:

    $ npm start
    or
    $ npm run build

Production build:

    $ npm run production

### Run the app

    $ cd server
    $ npm start

Note: by default, `npm start` will use the **development** build. To run the production
build, use the following command instead:

    $ npm start -- --client-environment=production

Open your browser on http://localhost:3000

#### Network access

By default, the server is setup to expose the Ext.Direct API through `localhost`. This
address can be changed via the [`direct.server`](server/config.json#L16) option (e.g.
`192.168.1.2`), in which case the client must be launched using the same address (e.g.
`https://192.168.1.2:3000`). If the client needs to be accessed with a different address,
you first need to enable CORS using [`cors.enabled: true`](server/config.json#L3).

#### Cordova / PhoneGap
If the app is ran inside
[Cordova (or PhoneGap)](https://docs.sencha.com/cmd/guides/cordova_phonegap.html), it's
required to change the following configs:

- change the Ext.Direct API endpoint in the client app ([`app.json#js`](client/app.json#L254)) by the absolute URL
- change the server IP/hostname ([`direct.server` option](server/config.json#L16)) by an accessible endpoint
- enable CORS ([`cors.enabled: true`](server/config.json#L3))
