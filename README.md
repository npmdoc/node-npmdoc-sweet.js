# api documentation for  [sweet.js (v2.2.1)](https://github.com/mozilla/sweet.js#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-sweet.js.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sweet.js) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sweet.js.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sweet.js)
#### Hygienic Macros for JavaScript

[![NPM](https://nodei.co/npm/sweet.js.png?downloads=true)](https://www.npmjs.com/package/sweet.js)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-sweet.js_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sweet.js/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tim Disney"
    },
    "ava": {
        "files": [
            "build/test/*.js",
            "build/test/declaration/*.js",
            "build/test/destructuring/**/*.js",
            "build/test/expressions/**/*.js",
            "build/test/modules/**/*.js",
            "build/test/statements/**/*.js",
            "!build/test/assertions.js"
        ]
    },
    "bin": {
        "sjs": "bin/sjs"
    },
    "browser": {
        "babel-core": false,
        "./build/src/node-module-loader.js": false,
        "./build/src/node-module-resolver.js": false
    },
    "bugs": {
        "url": "https://github.com/mozilla/sweet.js/issues"
    },
    "dependencies": {
        "babel-core": "^6.5.0",
        "immutable": "^3.7.4",
        "ramda": "^0.19.0",
        "ramda-fantasy": "^0.4.1",
        "resolve": "^1.1.7",
        "semver": "^5.3.0",
        "shift-codegen": "^4.0.0",
        "shift-js": "^0.2.1",
        "shift-parser": "^4.1.0",
        "shift-reducer": "^3.0.2",
        "shift-spidermonkey-converter": "^1.0.0",
        "sweet-spec": "1.1.0",
        "transit-js": "^0.8.846",
        "utils-dirname": "^1.0.0",
        "yargs": "^4.3.2"
    },
    "description": "Hygienic Macros for JavaScript",
    "devDependencies": {
        "asciidoctor-cli": "^1.5.2-alpha.3",
        "asciidoctor.js": "^1.5.4",
        "ava": "^0.15.0",
        "babel": "^6.5.0",
        "babel-cli": "^6.5.0",
        "babel-eslint": "^6.1.2",
        "babel-plugin-transform-flow-strip-types": "^6.14.0",
        "babel-preset-es2015-node5": "^1.2.0",
        "eslint": "^2.11.1",
        "eslint-plugin-flowtype": "^2.11.4",
        "event-stream": "^3.3.2",
        "expect.js": "0.3.x",
        "flow-bin": "^0.32.0",
        "nyc": "^6.0.0",
        "source-map": "~0.5.3",
        "source-map-support": "^0.4.0",
        "webpack": "^1.13.1"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "332929a0610821e61e364c141641cff72fd60d56",
        "tarball": "https://registry.npmjs.org/sweet.js/-/sweet.js-2.2.1.tgz"
    },
    "engines": {
        "node": ">5.0.0"
    },
    "gitHead": "22e5d182eb764d8427a7f447a69ad08ab777cb7a",
    "homepage": "https://github.com/mozilla/sweet.js#readme",
    "keywords": [
        "macros",
        "javascript"
    ],
    "license": "BSD-2-Clause",
    "licenses": [
        {
            "type": "BSD",
            "url": "http://github.com/mozilla/sweet.js/master/LICENSE.BSD"
        }
    ],
    "main": "dist/sweet.js",
    "maintainers": [
        {
            "name": "disnet",
            "email": "tim.disney@gmail.com"
        }
    ],
    "name": "sweet.js",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/mozilla/sweet.js.git"
    },
    "scripts": {
        "build": "npm run build:src && npm run build:test",
        "build:browser": "webpack build/src/sweet.js --output-library-target amd --output-library sweet",
        "build:src": "babel --out-dir build/src src",
        "build:test": "rsync -R test/**/*.js build & cp test/*.js build/test && babel --out-file build/test/assertions.js test/assertions.js",
        "clean": "rm -rf build",
        "dist": "npm run build && npm run build:browser && npm run docs && cp build/src/*.js dist",
        "docs": "asciidoctorjs doc/1.0/tutorial.adoc & asciidoctorjs doc/1.0/reference.adoc",
        "lint": "eslint src && flow",
        "prebuild": "npm run lint && mkdir -p build/test build/sweet dist/",
        "pretest": "npm run build",
        "report": "nyc ava && nyc report --reporter=html",
        "test": "npm run test:smoke",
        "test:curr": "ava build/test/modules/export.js",
        "test:full": "npm run build && ava",
        "test:smoke": "ava build/test/*.js !build/test/assertions.js"
    },
    "version": "2.2.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module sweet.js](#apidoc.module.sweet.js)
1.  [function <span class="apidocSignatureSpan">sweet.js.</span>compile (source)](#apidoc.element.sweet.js.compile)
1.  [function <span class="apidocSignatureSpan">sweet.js.</span>expand (source)](#apidoc.element.sweet.js.expand)
1.  [function <span class="apidocSignatureSpan">sweet.js.</span>parse (source, options)](#apidoc.element.sweet.js.parse)



# <a name="apidoc.module.sweet.js"></a>[module sweet.js](#apidoc.module.sweet.js)

#### <a name="apidoc.element.sweet.js.compile"></a>[function <span class="apidocSignatureSpan">sweet.js.</span>compile (source)](#apidoc.element.sweet.js.compile)
- description and source-code
```javascript
function compile(source) {
  let options = arguments.length <= 1 || arguments[1] === undefined ? {} : arguments[1];

  let ast = parse(source, options, options.includeImports);
  let gen = (0, _shiftCodegen2.default)(ast, new _shiftCodegen.FormattedCodeGen());
  return options.transform && !options.noBabel ? options.transform(gen, {
    babelrc: true,
    filename: options.filename
  }) : { code: gen };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sweet.js.expand"></a>[function <span class="apidocSignatureSpan">sweet.js.</span>expand (source)](#apidoc.element.sweet.js.expand)
- description and source-code
```javascript
function expand(source) {
  let options = arguments.length <= 1 || arguments[1] === undefined ? {} : arguments[1];

  let bindings = new _bindingMap2.default();
  let modules = new _modules.Modules({
    bindings: bindings,
    cwd: options.cwd || process.cwd(),
    filename: options.filename,
    transform: options.transform || _babelCore.transform || function (c) {
      return { code: c };
    },
    moduleResolver: options.moduleResolver || _nodeModuleResolver2.default,
    moduleLoader: options.moduleLoader || _nodeModuleLoader2.default
  });
  let compiledMod = modules.compileEntrypoint(source, options.filename, options.enforcePragma);
  let nativeImports = compiledMod.importEntries.filter(imp => !modules.has(imp.moduleSpecifier.val()));
  return new _terms2.default("Module", {
    directives: (0, _immutable.List)(),
    items: nativeImports.concat(compiledMod.body).concat(compiledMod.exportEntries.interpose(new _terms2.default('EmptyStatement
', {})))
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.sweet.js.parse"></a>[function <span class="apidocSignatureSpan">sweet.js.</span>parse (source, options)](#apidoc.element.sweet.js.parse)
- description and source-code
```javascript
function parse(source, options) {
  let includeImports = arguments.length <= 2 || arguments[2] === undefined ? true : arguments[2];

  return (0, _shiftReducer2.default)(new _parseReducer2.default({ phase: 0 }), expand(source, options).gen(includeImports));
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
