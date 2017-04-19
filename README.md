# npmdoc-sweet.js

#### api documentation for  [sweet.js (v3.0.3)](https://github.com/sweet-js/sweet.js#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-sweet.js.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sweet.js) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sweet.js.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sweet.js)

#### Hygienic Macros for JavaScript

[![NPM](https://nodei.co/npm/sweet.js.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/sweet.js)

- [https://npmdoc.github.io/node-npmdoc-sweet.js/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-sweet.js/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sweet.js/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sweet.js/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tim Disney"
    },
    "ava": {
        "babel": "inherit",
        "files": [
            "test/unit/*.js"
        ],
        "require": [
            "babel-register"
        ]
    },
    "bin": {
        "sjs": "bin/sjs"
    },
    "browser": {
        "babel-core": false
    },
    "bugs": {
        "url": "https://github.com/sweet-js/sweet.js/issues"
    },
    "dependencies": {
        "babel-core": "^6.18.0",
        "immutable": "^3.7.4",
        "prettier": "^1.1.0",
        "prettier-eslint": "^5.1.0",
        "ramda": "^0.22.0",
        "ramda-fantasy": "^0.6.0",
        "readtable": "^0.0.1",
        "resolve": "^1.1.7",
        "semver": "^5.3.0",
        "shift-codegen": "^4.0.0",
        "shift-js": "^0.2.1",
        "shift-reducer": "^3.0.2",
        "shift-spidermonkey-converter": "^1.0.0",
        "sweet-spec": "3.1.0",
        "transit-js": "^0.8.846",
        "utils-dirname": "^1.0.0",
        "yargs": "^4.3.2"
    },
    "description": "Hygienic Macros for JavaScript",
    "devDependencies": {
        "angular": "1.6.0",
        "asciidoctor-cli": "^1.5.2-alpha.3",
        "asciidoctor.js": "^1.5.4",
        "ava": "^0.18.2",
        "babel-cli": "^6.18.0",
        "babel-eslint": "^7.0.0",
        "babel-plugin-transform-flow-strip-types": "^6.14.0",
        "babel-preset-node7": "1.4.0",
        "babel-register": "6.18.0",
        "eslint": "^3.7.1",
        "eslint-plugin-flowtype": "^2.11.4",
        "event-stream": "^3.3.2",
        "expect.js": "0.3.x",
        "flow-bin": "^0.39.0",
        "husky": "^0.13.2",
        "jquery": "3.1.1",
        "lint-staged": "^3.3.1",
        "nyc": "^6.0.0",
        "prettier-eslint-cli": "^3.1.2",
        "source-map": "~0.5.3",
        "source-map-support": "^0.4.0",
        "webpack": "^1.13.1"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "9518e4c309f19a88007c74000edead9fb2822142",
        "tarball": "https://registry.npmjs.org/sweet.js/-/sweet.js-3.0.3.tgz"
    },
    "engines": {
        "node": ">=7.0.0"
    },
    "gitHead": "d871fef53532d94fc8d47bdce7f565a1846dc478",
    "homepage": "https://github.com/sweet-js/sweet.js#readme",
    "keywords": [
        "macros",
        "javascript"
    ],
    "license": "BSD-2-Clause",
    "licenses": [
        {
            "type": "BSD",
            "url": "http://github.com/sweet-js/sweet.js/master/LICENSE.BSD"
        }
    ],
    "lint-staged": {
        "*.js": [
            "prettier-eslint --write",
            "git add"
        ]
    },
    "main": "dist/sweet.js",
    "maintainers": [
        {
            "name": "disnet"
        }
    ],
    "name": "sweet.js",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/sweet-js/sweet.js.git"
    },
    "scripts": {
        "build": "npm run build:src && npm run build:browser",
        "build:browser": "cp helpers.js browser/scripts/ && webpack build/src/browser-sweet.js --output-library-target umd --output-library sweet",
        "build:src": "babel --out-dir build/src src",
        "clean": "rm -rf build",
        "dist": "rsync -r build/src/ dist",
        "docs": "asciidoctorjs doc/1.0/tutorial.adoc & asciidoctorjs doc/1.0/reference.adoc",
        "format": "prettier-eslint --write \"src/**/*.js\" \"test/**/*.js\"",
        "lint": "eslint src test && flow",
        "prebuild": "mkdir -p build/test build/sweet dist/",
        "precommit": "lint-staged",
        "preprofile": "npm run build",
        "prepublish": "npm run build && npm run dist",
        "pretest": "npm run lint",
        "profile": "node --prof profile.js && node --prof-process *v8.log > v8-processed.log && rm *v8.log",
        "report": "nyc ava && nyc report--reporter=html",
        "test": "ava",
        "test:262": "ava test/parser/test-run-test262.js",
        "test:ci": "npm run pretest && ava && ava test/parser/test-*.js"
    },
    "version": "3.0.3",
    "warnings": [
        {
            "code": "ENOTSUP",
            "required": {
                "node": ">=7.0.0"
            },
            "pkgid": "sweet.js@3.0.3"
        },
        {
            "code": "ENOTSUP",
            "required": {
                "node": ">=7.0.0"
            },
            "pkgid": "sweet.js@3.0.3"
        }
    ]
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
