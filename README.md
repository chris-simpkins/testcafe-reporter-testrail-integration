# testcafe-reporter-testrail-integration

This is the **testrail-integration** reporter plugin for [TestCafe](http://devexpress.github.io/testcafe).

## Install

```
npm install testcafe-reporter-testrail-integration
```

## Setup

This reporter makes use of [dotenv](https://www.npmjs.com/package/dotenv). To define environment variables, create a file `.env` at the root of your testcafe directory with the following vars:

```
TESTRAIL_ENABLE=true
PUSH_TEST_RUNS=true
PLAN_NAME=<plan name>
TESTRAIL_HOST=<testRail URL>
TESTRAIL_USER=<testRail email login>
TESTRAIL_PASS=<testRail password or api auth>
PROJECT_NAME=<project name>
SUITE_NAME=<suite name> (default is Master if project contains single suite)
RUN_NAME=<run name>
UPDATE_TEST_CASES=<option to update existing test cases>
```

For the reporter to be able to update testcases with run results, you must define testcases in the following format:

```
test('<Section name>|<Testcase>|<Testrail case code>', func => {

}

//EXAMPLE:

test('Home Page|User is able to click on something|C567', func => {

}
```

### Optional

If you have any skipped test cases, you will need to make a custom `Skipped` status in your testRail project, otherwise the reporter will fail to publish results.

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

## Improvements

Please PR any improvements / fixes. A lot of this code is from another broken + deprecated testRail reporter for TestCafe which I quickly fixed up. A lot of the code needs refactoring / improving, I just had to perform quick fixes and improvements.

## Author
Chris Simpkins 
