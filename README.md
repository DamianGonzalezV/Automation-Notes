# Automation-Notes


Table of Contents


Intro
This cheat sheet is a personal reference designed to reinforce key concepts related to QA automation, specifically with a JavaScript-oriented approach. It covers the most important tools, frameworks and practices needed to master, including Cypress, Playwright, GitHub, Postman, and Jenkins. 
Cypress

Cypress is a JavaScript based test automation tool and framework for web developers, Cypress can be used for E2E tests or Component tests. 
What is E2E?
E2E tests the complete application workflow. The goal is to confirm that all components function together as intended from start to the end of a process.

E2E tests typically cover things like:

Logging in
Performing a transaction
Submitting a form
Installing Cypress
Before installing cypress, we need to have a package.json file in the root of our project. We can run the following command:  npm init -y   

To install cypress we run npm install cypress -save-dev  this installs cypress locally as a dev dependency for our project and allows us for scripting with npm commands.
Open the Cypress app
To open Cypress for the first time or reopen Cypress we use the following command: npx cypress open  the cypress launchpad will open
Run cypress headlessly
npx cypress run

Adding npm Scripts
We can add Cypress commands to the scripts field in our package.json file, as in the following script to open cypress:

{
 "scripts": {
   "cy:open": "cypress open"
 }
}

Cypress commands can be saved as scripts, the following command run headlessly with the chrome browser cypress run -browser chrome

Test file structure
Cypress test files are usually placed under cypress/e2e/ each file typically corresponds to a feature, page, or user flow. 
How Cypress tests are organized
describe()
it()
beforeEach()
cy()

To define a test suite, a group of related tests we use the describe() function
describe("Paying flow", () => {});

with it() we can define individual test cases inside describe, it needs a function body
describe("Paying flow", () => {
  it("Should successfully complete a payment", () => {});
});

Test hooks like beforeEach() for setup/teardown logic like visiting a URL with cy.visit()
describe("Paying flow", () => {
  beforeEach(() => {
    cy.visit("");
  });
  it("Should successfully complete a payment", () => {});
});

cy() cypress object
cy is the cypress global object, provides access to all cypress commands, like
Interacting with the DOM
Making assertions
Handling browser actions (assert the URL, go back in history, and reload the page — all browser-level actions)
