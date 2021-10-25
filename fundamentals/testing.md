---

copyright:
  years: 2021
lastupdated: "2021-10-25"

subcollection: sdk-handbook

---

# Testing

## Unit testing

The SDK MUST have unit tests for each service which include both positive and negative tests of each operation.
The negative tests should exercise some of the most common error conditions (missing parameter or property, invalid JSON response body, etc.).
In this context, the term "unit tests" refers to the fact that the tests may use mocking to simulate the service endpoint's behavior,
rather than interacting with an actual service endpoint.
The goal of the unit tests is to provide broad coverage of the generated SDK code to verify that it works correctly in isolation.
Note that if you use the IBM SDK generator to build your SDK, it will produce suitable unit test code for the
main SDK languages (Go, Java, Node.js, and Python).

## Integration testing

The SDK MUST have integration tests for each service which use an actual instance of the service endpoint to verify that the generated SDK
code works properly with the service endpoint implementation. This, in turn, verifies the correctness of the service's API definition.

The integration tests MUST contain, at a minimum, a positive test involving each operation
of the service.   Additionally, the integration tests SHOULD include tests of common error conditions, ideally including
tests involving each error status code that is defined in the service's API definition.

### Guidelines for integration tests

Integration tests MUST:
* Use an actual instance of the service endpoint
* Include positive tests of each operation
* Use realistic values for operation parameters and model properties

Integration tests SHOULD:
* Include negative tests of common error conditions
* Include tests involving each error response status code defined in the service's API definition
* Excercise pagination for each "list"-type operation that supports pagination
