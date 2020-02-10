# testcafe-reporter-testrail-integration
[![Build Status](https://travis-ci.org/chris-simpkins/testcafe-reporter-testrail-integration.svg)](https://travis-ci.org/chris-simpkins/testcafe-reporter-testrail-integration)

This is the **testrail-integration** reporter plugin for [TestCafe](http://devexpress.github.io/testcafe).

<p align="center">
    <img src="https://raw.github.com/chris-simpkins/testcafe-reporter-testrail-integration/master/media/preview.png" alt="preview" />
</p>

## Install

```
npm install testcafe-reporter-testrail-integration
```

## Usage

When you run tests from the command line, specify the reporter name by using the `--reporter` option:

```
testcafe chrome 'path/to/test/file.js' --reporter testrail-integration
```


When you use API, pass the reporter name to the `reporter()` method:

```js
testCafe
    .createRunner()
    .src('path/to/test/file.js')
    .browsers('chrome')
    .reporter('testrail-integration') // <-
    .run();
```

## Author
Chris Simpkins 
