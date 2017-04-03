# api documentation for  [grunt-browserify (v5.0.0)](https://github.com/jmreidy/grunt-browserify)  [![npm package](https://img.shields.io/npm/v/npmdoc-grunt-browserify.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-grunt-browserify) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-grunt-browserify.svg)](https://travis-ci.org/npmdoc/node-npmdoc-grunt-browserify)
#### Grunt task for node-browserify

[![NPM](https://nodei.co/npm/grunt-browserify.png?downloads=true)](https://www.npmjs.com/package/grunt-browserify)

[![apidoc](https://npmdoc.github.io/node-npmdoc-grunt-browserify/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-grunt-browserify_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-grunt-browserify/build..beta..travis-ci.org/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-grunt-browserify/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-grunt-browserify/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/jmreidy/grunt-browserify/issues"
    },
    "contributors": [
        {
            "name": "Justin Reidy",
            "email": "jmreidy@rzrsharp.net"
        },
        {
            "name": "Tommy Leunen",
            "email": "tommy.leunen@gmail.com"
        }
    ],
    "dependencies": {
        "async": "^1.5.0",
        "browserify": "^13.0.0",
        "glob": "^6.0.3",
        "lodash": "^3.10.1",
        "resolve": "^1.1.6",
        "watchify": "^3.6.1"
    },
    "description": "Grunt task for node-browserify",
    "devDependencies": {
        "grunt": "^0.4.5",
        "grunt-cli": "^0.1.13",
        "grunt-contrib-clean": "^0.7.0",
        "grunt-contrib-jshint": "^0.11.3",
        "mocha": "^2.3.4",
        "sinon": "^1.17.2"
    },
    "directories": {},
    "dist": {
        "shasum": "1d333ca98bdac44576f646e0d6680087cbf8c615",
        "tarball": "https://registry.npmjs.org/grunt-browserify/-/grunt-browserify-5.0.0.tgz"
    },
    "engines": {
        "node": ">= 0.8.x"
    },
    "files": [
        "lib/",
        "tasks/"
    ],
    "gitHead": "b26e20fe19ba31dbf0aec659eba2fd2982ab81f0",
    "homepage": "https://github.com/jmreidy/grunt-browserify",
    "keywords": [
        "gruntplugin",
        "browserify",
        "grunt"
    ],
    "licenses": [
        {
            "type": "MIT",
            "url": "https://github.com/jmreidy/grunt-browserify/blob/master/LICENSE-MIT"
        }
    ],
    "main": "tasks/browserify.js",
    "maintainers": [
        {
            "name": "jmreidy",
            "email": "jmreidy@rzrsharp.net"
        },
        {
            "name": "tleunen",
            "email": "tommy.leunen@gmail.com"
        }
    ],
    "name": "grunt-browserify",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/jmreidy/grunt-browserify.git"
    },
    "scripts": {
        "test": "mocha -R spec --timeout 5000"
    },
    "version": "5.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module grunt-browserify](#apidoc.module.grunt-browserify)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.</span>runTask (grunt, options, file, next)](#apidoc.element.grunt-browserify.runTask)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.</span>runner (options)](#apidoc.element.grunt-browserify.runner)
1.  object <span class="apidocSignatureSpan">grunt-browserify.</span>runner.prototype

#### [module grunt-browserify.runner](#apidoc.module.grunt-browserify.runner)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.</span>runner (options)](#apidoc.element.grunt-browserify.runner.runner)

#### [module grunt-browserify.runner.prototype](#apidoc.module.grunt-browserify.runner.prototype)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>createDestDir (destination)](#apidoc.element.grunt-browserify.runner.prototype.createDestDir)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>keepAliveFn (destination)](#apidoc.element.grunt-browserify.runner.prototype.keepAliveFn)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>onBundleComplete (destination, options, next)](#apidoc.element.grunt-browserify.runner.prototype.onBundleComplete)
1.  [function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>run (files, destination, options, next)](#apidoc.element.grunt-browserify.runner.prototype.run)



# <a name="apidoc.module.grunt-browserify"></a>[module grunt-browserify](#apidoc.module.grunt-browserify)

#### <a name="apidoc.element.grunt-browserify.runTask"></a>[function <span class="apidocSignatureSpan">grunt-browserify.</span>runTask (grunt, options, file, next)](#apidoc.element.grunt-browserify.runTask)
- description and source-code
```javascript
runTask = function (grunt, options, file, next) {
  var runner = new Runner({
    writer: grunt.file,
    logger: grunt,
    browserify: browserify,
    watchify: watchify
  });
  var files = grunt.file.expand({filter: 'isFile'}, file.src).map(function (f) {
    return path.resolve(f);
  });
  runner.run(files, file.dest, options, next);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.grunt-browserify.runner"></a>[function <span class="apidocSignatureSpan">grunt-browserify.</span>runner (options)](#apidoc.element.grunt-browserify.runner)
- description and source-code
```javascript
function GruntBrowserifyRunner(options) {
  this.browserify = options.browserify;
  this.watchify = options.watchify;
  this.logger = options.logger;
  this.writer = options.writer;
  this.firstBuild = true;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.grunt-browserify.runner"></a>[module grunt-browserify.runner](#apidoc.module.grunt-browserify.runner)

#### <a name="apidoc.element.grunt-browserify.runner.runner"></a>[function <span class="apidocSignatureSpan">grunt-browserify.</span>runner (options)](#apidoc.element.grunt-browserify.runner.runner)
- description and source-code
```javascript
function GruntBrowserifyRunner(options) {
  this.browserify = options.browserify;
  this.watchify = options.watchify;
  this.logger = options.logger;
  this.writer = options.writer;
  this.firstBuild = true;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.grunt-browserify.runner.prototype"></a>[module grunt-browserify.runner.prototype](#apidoc.module.grunt-browserify.runner.prototype)

#### <a name="apidoc.element.grunt-browserify.runner.prototype.createDestDir"></a>[function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>createDestDir (destination)](#apidoc.element.grunt-browserify.runner.prototype.createDestDir)
- description and source-code
```javascript
createDestDir = function (destination) {
  var destPath = path.dirname(path.resolve(destination));
  if (!this.writer.exists(destPath)) {
    this.writer.mkdir(destPath);
  }
  return destPath;
}
```
- example usage
```shell
...
if (options.plugin) {
  _.forEach(options.plugin, function (plugin) {
    b.plugin(plugin);
  });
}


var destPath = this.createDestDir(destination);
var keepAlive = this.keepAliveFn.bind(this, destination);
var done = options.keepAlive? keepAlive : next;
var bundleComplete = this.onBundleComplete(destination, options, done);

if (options.watch) {
  var bundleUpdate = this.onBundleComplete(destination, options, keepAlive);
  b.on('update', function (ids) {
...
```

#### <a name="apidoc.element.grunt-browserify.runner.prototype.keepAliveFn"></a>[function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>keepAliveFn (destination)](#apidoc.element.grunt-browserify.runner.prototype.keepAliveFn)
- description and source-code
```javascript
keepAliveFn = function (destination) {
  //this.logger.log.ok('Watchifying...');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.grunt-browserify.runner.prototype.onBundleComplete"></a>[function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>onBundleComplete (destination, options, next)](#apidoc.element.grunt-browserify.runner.prototype.onBundleComplete)
- description and source-code
```javascript
onBundleComplete = function (destination, options, next) {
  var self = this;
  return function (err, buf) {
    if (err) {
      self.logger.log.error(err);
      if (self.firstBuild || !options.keepAlive) {
        self.logger.fail.warn('Error running grunt-browserify.');
      }
    }
    else if (buf) {
        // prepend the banner
        if(options.banner) {
            buf = Buffer.concat([new Buffer(options.banner + '\n', 'utf8'), buf]);
        }

      self.logger.log.ok('Bundle ' + destination.cyan + ' created. ' + (options.keepAlive ? 'Watchifying...' : ''));
      self.writer.write(destination, buf);
    }

    self.firstBuild = false;
    next();
  };
}
```
- example usage
```shell
...
  });
}


var destPath = this.createDestDir(destination);
var keepAlive = this.keepAliveFn.bind(this, destination);
var done = options.keepAlive? keepAlive : next;
var bundleComplete = this.onBundleComplete(destination, options, done);

if (options.watch) {
  var bundleUpdate = this.onBundleComplete(destination, options, keepAlive);
  b.on('update', function (ids) {
    ids.forEach(function (id) {
      self.logger.log.ok(id.cyan + ' changed, updating bundle.');
    });
...
```

#### <a name="apidoc.element.grunt-browserify.runner.prototype.run"></a>[function <span class="apidocSignatureSpan">grunt-browserify.runner.prototype.</span>run (files, destination, options, next)](#apidoc.element.grunt-browserify.runner.prototype.run)
- description and source-code
```javascript
run = function (files, destination, options, next) {
  var self = this;

  //set constructor options and instantiate
  var bOpts = _.cloneDeep(options.browserifyOptions) || {};
  bOpts.entries = bOpts.entries || files;

  // watchify options
  var wOpts = options.watchifyOptions || {};

  // Watchify requires specific arguments
  if(options.watch) {
    bOpts = _.extend({ cache: {}, packageCache: {} }, bOpts);
  }

  //determine watchify or browserify
  var b = options.watch ? this.watchify(this.browserify(bOpts), wOpts) : this.browserify(bOpts);

  b.on('error', function (err) {
    self.logger.fail.warn(err);
  });

  if(options.bundleOptions) {
    throw new Error('bundleOptions is no longer used. Move all option in browserifyOptions.');
  }

  if(options.alias) {
    if(_.isPlainObject(options.alias)) {
      for(var alias in options.alias) {
        b.require(options.alias[alias], {expose: alias});
      }
    }
    else {
      requireFiles(b, options.alias);
    }
  }

  if(options.require) {
    requireFiles(b, options.require);
  }

  if (options.exclude) {
    _.forEach(options.exclude, function (file) {
      runOptionForGlob(b, 'exclude', file);
    });
  }

  if (options.ignore) {
    _.forEach(options.ignore, function (file) {
      runOptionForGlob(b, 'ignore', file);
    });
  }

  if (options.external) {
    // allow externalizing of alias object
    if(_.isPlainObject(options.external)) {
      for(var id in options.external) {
        if (testForGlob(id)) {
          runOptionForGlob(b, 'external', id);
        }
        else {
          b.external(id);
        }
      }
    }
    else {
      _.forEach(options.external, function (id) {
        //allow externalizing of require lists
        if (id.match(':')) {
          id = id.split(':')[1];
        }

        if (testForGlob(id)) {
          runOptionForGlob(b, 'external', id);
        }
        else {
          b.external(id);
        }
      });
    }
  }

  if (options.transform) {
    _.forEach(options.transform, function (transformer) {
      b.transform(transformer);
    });
  }

  if (options.plugin) {
    _.forEach(options.plugin, function (plugin) {
      b.plugin(plugin);
    });
  }


  var destPath = this.createDestDir(destination);
  var keepAlive = this.keepAliveFn.bind(this, destination);
  var done = options.keepAlive? keepAlive : next;
  var bundleComplete = this.onBundleComplete(destination, options, done);

  if (options.watch) {
    var bundleUpdate = this.onBundleComplete(destination, options, keepAlive);
    b.on('update', function (ids) {
      ids.forEach(function (id) {
        self.logger.log.ok(id.cyan + ' changed, updating bundle.');
      });
      doBundle(b, options, bundleUpdate);
    });
  }

  if (options.configure) {
    options.configure(b);
  }

  doBundle(b, options, bundleComplete);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
