## App set-up

This is an empty repo to use as a set-up for an app - not a plugin or library. There aren't that many differences, but a few (like no `index.js`, no namespacing considerations for the object that gets exposed with a plugin, bundling as an IIFE, not a UMD module)

### Fundaments

The `index.html` and the `src/app.js` is where the coding happens. `app.js` is the app's entry point and should get additional functions and modules via `import`s.

Note, there's no CSS file here. This should probably be added?

### Rollup

Rollup bundles our JS. `src/app.js` in, `dist/bundle.js` and `dist/bundle.min.js` out. Simple. For now it considers a couple of plugins:

* Babel (to transpile)
* node-resolve (to find files in `node_modules`)
* CommonJS (to deal with `require()`) and 
* Uglify (your guess...)

[Check the file](https://github.com/larsvers/app-setup/blob/master/rollup.config.js) for more details.

### Babel

Bable is transpiling our JS shlonk and does so with the most mnml of all settings ( [really](https://github.com/larsvers/app-setup/blob/master/.babelrc) ). We just have to make sure it does play well with rollup - the babel plugin takes care of this.

### Dependencies and Scripts

Check out the [package.json](https://github.com/larsvers/app-setup/blob/master/package.json) for the dependencies. Nothing too special, including D3, a few key plugins and topojson. 

The scripts are simply building, watching or uglifying. There's lots more one can do but this is being kept simple. 

🐕