# npmtest-mobx

#### basic test coverage for  [mobx (v3.1.9)](https://mobxjs.github.io/mobx)  [![npm package](https://img.shields.io/npm/v/npmtest-mobx.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-mobx) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-mobx.svg)](https://travis-ci.org/npmtest/node-npmtest-mobx)

#### Simple, scalable state management.

[![NPM](https://nodei.co/npm/mobx.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/mobx)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-mobx/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-mobx/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-mobx/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-mobx/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-mobx/build/test-report.html)|
| test-server-github : | [![github.com test-server](https://npmtest.github.io/node-npmtest-mobx/GitHub-Mark-32px.png)](https://npmtest.github.io/node-npmtest-mobx/build/app/index.html) | | build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-mobx/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-mobx/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-mobx/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-mobx/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-mobx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-mobx/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-mobx/build/test-report.html](https://npmtest.github.io/node-npmtest-mobx/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-mobx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-mobx/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-mobx/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-mobx/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-mobx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-mobx/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-mobx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-mobx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Michel Weststrate"
    },
    "bugs": {
        "url": "https://github.com/mobxjs/mobx/issues"
    },
    "dependencies": {},
    "description": "Simple, scalable state management.",
    "devDependencies": {
        "babel-cli": "^6.4.5",
        "babel-core": "^6.4.5",
        "babel-plugin-transform-decorators-legacy": "^1.3.4",
        "babel-preset-es2015": "^6.3.13",
        "babel-preset-react": "^6.3.13",
        "babel-preset-stage-1": "^6.3.13",
        "babelify": "^7.3.0",
        "browserify": "^12.0.1",
        "coveralls": "^2.11.4",
        "faucet": "0.0.1",
        "flow-bin": "0.36.0",
        "istanbul": "^0.3.21",
        "iterall": "^1.0.2",
        "lodash.intersection": "^3.2.0",
        "ncp": "^2.0.0",
        "rimraf": "^2.5.4",
        "tape": "^4.2.2",
        "tape-run": "^2.1.0",
        "typescript": "^2.1.4",
        "uglify-js": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "ed4af9d874ff6032c7af91fc1b87d9d33122a557",
        "tarball": "https://registry.npmjs.org/mobx/-/mobx-3.1.9.tgz"
    },
    "files": [
        "lib",
        "LICENSE",
        "bower.json"
    ],
    "gitHead": "c796b50fec547e9a411b6f535e50e9b09afc3194",
    "homepage": "https://mobxjs.github.io/mobx",
    "keywords": [
        "mobx",
        "mobservable",
        "observable",
        "react-component",
        "react",
        "reactjs",
        "reactive",
        "model",
        "frp",
        "functional-reactive-programming",
        "state management",
        "data flow"
    ],
    "license": "MIT",
    "main": "lib/mobx.js",
    "maintainers": [
        {
            "name": "mweststrate"
        }
    ],
    "name": "mobx",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mobxjs/mobx.git"
    },
    "scripts": {
        "_prepublish": "npm run small-build",
        "build-babel-tests": "babel test/babel/babel-tests.js -o test/babel-tests.js",
        "build-tests": "npm run build-typescript-tests && npm run build-babel-tests",
        "build-typescript-tests": "tsc -p test/typescript",
        "coverage": "npm run quick-build && npm run build-tests && istanbul cover tape test/*.js test/typescript/typescript-tests.js",
        "full-test": "npm run small-build && npm run build-tests && npm run use-minified && npm run tape && node --expose-gc test/perf/index.js && npm run test-flow && node test/mixed-versions/mixed-versions.js",
        "lint": "tslint -c tslint.json src/*.ts src/types/*.ts src/api/*.ts src/core/*.ts src/utils/*.ts",
        "perf": "npm run small-build && PERSIST=true time node --expose-gc test/perf/index.js",
        "quick-build": "tsc --pretty",
        "small-build": "node scripts/single-file-build.js",
        "tape": "tape test/*.js test/typescript/typescript-tests.js | faucet",
        "test": "npm run quick-build && npm run tape",
        "test-browser-chrome": "npm run small-build && ( browserify test/*.js | tape-run --browser chrome | faucet )",
        "test-browser-electron": "npm run small-build && ( browserify test/*.js | tape-run | faucet )",
        "test-browser-firefox": "npm run small-build && ( browserify test/*.js  | tape-run --browser firefox | faucet )",
        "test-browser-safari": "npm run small-build && ( browserify test/*.js -t [ babelify --presets [ es2015 ] ] | tape-run --browser safari | faucet )",
        "test-flow": "flow check",
        "test-travis": "npm run full-test && npm run quick-build && istanbul cover tape test/*.js test/typescript/typescript-tests.js",
        "use-minified": "cp lib/mobx.min.js lib/mobx.js"
    },
    "typings": "lib/mobx.d.ts",
    "umd:main": "lib/mobx.umd.js",
    "version": "3.1.9",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
