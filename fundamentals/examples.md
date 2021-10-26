---

copyright:
  years: 2021
lastupdated: "2021-10-25"

subcollection: sdk-handbook

---

# Examples
{: #sdk-examples}

## SDK working examples
{: #working-examples}

The SDK SHOULD contain a set of working examples for each service contained in the SDK.
These working examples SHOULD provide a clear, concise example of how to use each operation within the service.

These examples SHOULD be relatively easy for users to execute, similar to test cases contained in the SDK.

### Guidelines for examples
{: #example-guidelines}

The SDK examples for a service SHOULD:
* Include a clear, concise example of how to invoke each operation
* Use realistic values for operation parameters and model properties which enhance the user's understanding of the operation
* Use consistent parameter/property values across the various SDK languages (Go, Java, Node.js, and Python) as well as Curl;
ideally, the parameter/property values used in the examples code are defined within "example" fields in the service's API definition

The examples can be used to provide the example code fragments displayed in the service's API Reference docs.
