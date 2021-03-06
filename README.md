# TestRail Reporter for posting TestRun for Cypress based on Post true OR False flag

[![version]](https://www.npmjs.com/package/testrail-reporter-with-flag-for-cypress)
[![downloads]](https://www.npmjs.com/package/testrail-reporter-with-flag-for-cypress)
[![MIT License]](https://github.com/shrutirathee/testrail-reporter-with-flag-for-cypress/blob/main/LICENSE)

Publishes [Cypress](https://www.cypress.io/) runs on TestRail if the Flag "postToTestrail" is set to "true"

Cloned from the original package [cypress-testrail-reporter](https://github.com/Vivify-Ideas/cypress-testrail-reporter) by [Milutin Savovic](https://github.com/mickosav)

Allows you to set statuses for test cases in a specific TestRun.

## Install

```shell
$ npm i testrail-reporter-with-flag-for-cypress
$ yarn add testrail-reporter-with-flag-for-cypress
```

## Usage

Add reporter to your `cypress.json`:

```json
...
{
 "reporter": "testrail-reporter-with-flag-for-cypress",
  "reporterOptions": {
    "host": "https://yourdomain.testrail.io",
    "username": "username",
    "password": "password / API token",
    "postToTestrail": true OR false,
    "projectId": idNumber,
    "runId": testRunNumber
}
```

Your Cypress tests should include the ID of your TestRail test case. Make sure your test case IDs are distinct from your test titles:

```Javascript
// Good:
it("C123 C124 Can authenticate a valid user", ...
it("Can authenticate a valid user C321", ...

// Bad:
it("C123Can authenticate a valid user", ...
it("Can authenticate a valid userC123", ...
```

## Reporter Options

**host**: _string_ domain name of your TestRail instance (e.g. for a hosted instance _https://instance.testrail.com_).

**username**: _string_ email of the user under which the test run will be created.

**password**: _string_ password or the API key for the aforementioned user.

**postToTestrail**: _boolean_ true to post results to sepcified run or false to not post any resluts

**projectId**: _number_ project with which the tests are associated.

**runId**: _number_ a specific test run id number.

## TestRail Settings

To increase security, the TestRail team suggests using an API key instead of a password. You can see how to generate an API key [here](http://docs.gurock.com/testrail-api2/accessing#username_and_api_key).

If you maintain your own TestRail instance on your own server, it is recommended to [enable HTTPS for your TestRail installation](http://docs.gurock.com/testrail-admin/admin-securing#using_https).

For TestRail hosted accounts maintained by [Gurock](http://www.gurock.com/), all accounts will automatically use HTTPS.

You can read the whole TestRail documentation [here](http://docs.gurock.com/).

## Author

Author: Shruti Rathee - [github](https://github.com/shrutirathee)

## License

This project is licensed under the [MIT license](/LICENSE.md).

## Acknowledgments

* [Milutin Savovic](https://github.com/mickosav), author of the [cypress-testrail-reporter](https://github.com/Vivify-Ideas/cypress-testrail-reporter) repository that was cloned.
* [Pierre Awaragi](https://github.com/awaragi), owner of the [mocha-testrail-reporter](https://github.com/awaragi/mocha-testrail-reporter) repository that was forked.