# Cypress
Cypress front end testing tool

https://www.cypress.io/

Cypress is a next generation front end testing tool built for the modern web. We address the key pain points developers and QA engineers face when testing modern applications.

## Contents
- [Usage](#usage)
- [Writing Tests](#writing-tests)


## Usage
To set up Cypress
```
npm install cypress --save-dev
```

To start Cypress
```
cypress open
```

Or with Node pacakge manager(in VSCode)
```
npx cypress open
```

Cypress users are typically developers or QA engineers building web applications using modern JavaScript frameworks.

Cypress enables you to write all types of tests:
    End-to-end tests
    Component tests
    Integration tests
    Unit tests

Cypress can test anything that runs in a browser.


## Writing Tests

Test structure
```
descirbe('name of the suite', () => {
  before(() => {
    // before everything once
  })

  beforeEach(() => {
    // before each test
  })

  after(() => {
    // one time after everything
  })

  afterEach(() => {
    // after each test
  })

  it(() => {
    // HERE GOES TEST
  })
})
```

* **cy** - marks for command chain in Cypress. For example: cy.visit('https://example.com');
* **only** - keyword (i.e. it.only) with only keyword marked tests will run if there is no need to run all the tests
* **skip** - keyword (i.e. it.skip) can be used to mark test that are for example not fully written yet to skip those

GET Commands
* **visit** - visit page to test. Example: .visit('https://example.com')
* **get** - select HTML DOM element. Example: .get('input[type="username"]')
SET Commands
* **click** - click on selected element. Example .click()
* **type** - type text on selected element. Example: .type('my_password')

Selectors
* **#username** - element id
* **'h2'** - for selecting h2 element on page

* **should** - assertion. For example:
```
.should('have.css', 'display', 'none')
.should('be.visible')
.should('not.be.visible')
``` 
* **contains** - locator. For example:
```
.contains('Password')
``` 

To perform assertions:
```
cy.url().should('include', '/dashboard');
cy.get('.welcome-message').should('contain', 'Welcome, John Doe');
```
