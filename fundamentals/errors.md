---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Errors

## Error delivery

SDK methods MUST surface errors to the caller in the manner that is idiomatic for the particular language.
For example, a Go SDK should return an error value from the method, but a Java SDK should raise an Exception.

## Error content

When an SDK method encounters an error, it MUST capture all relevant information about the error and return it
in the error structure returned to the caller.  This includes the entire contents of the error response and all
response headers.  The SDK documentation must clearly describe how this information is returned and how it can
be accessed by the calling program.

Errors that are generated within the SDK MUST give a clear and specific description of the problem.
For example, if a method parameter failed a validation, the message should state which parameter is invalid
and the reason it is invalid.
