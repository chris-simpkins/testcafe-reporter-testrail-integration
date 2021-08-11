# testcafe-reporter-testrail-integration

This is the **testrail-integration** reporter plugin for [TestCafe](http://devexpress.github.io/testcafe).

## Install

```
npm install testcafe-reporter-testrail-integration
```

## Setup

This package uses environment variables, make sure required variables are accessible by the process.

```
TESTRAIL_ENABLE=<bool - optional> [default true]
PUSH_TEST_RUNS=<bool - optional> [default true]
PLAN_NAME=<string>
TESTRAIL_HOST=<string> [format - https://org.testrail.io]
TESTRAIL_USER=<string>
TESTRAIL_PASS=<string> [password or api key]
PROJECT_NAME=<string>
SUITE_NAME=<string - optional> [default "Master"]
RUN_NAME=<string - optional> [default "TestAutomation_Plan"]
UPDATE_TEST_CASES=<bool - optional> [default true]
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

Please PR any improvements / fixes. A lot of this code is from another broken + deprecated testRail reporter for TestCafe which I quickly fixed up.

## Author
Chris Simpkins 
