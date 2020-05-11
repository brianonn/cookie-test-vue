# Vuejs test app

This app was created with the vue-cli.

If you don't already have the vue cli installed, you can install it like this:
```shell
$ npm install -g @vue/cli
```

Once you have the vue cli installed, you can create an application boilerplate that uses webpack and the vue-loader:

```shell
$ vue create cookie-test-vue
```

To start the development server, use

```shell
$ npm run serve
```

This will start up a server on [localhost:8080](https://localhost:8080/) that is continually watching for changes in the source tree
and will recompile and hot-reload the app when a source change is made.

When you are finished development, you can create a production build in the `dist` folder by running:

```shell
$ npm run build
```

Running this build script will compile and package the application into the `dist` folder which can be deployed. 

You can test the `dist` folder deployment by running a standalone webserver:

```shell
$ cd dist
$ python2 -mSimpleHTTPServer 
```

