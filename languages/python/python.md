---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Python
{: #python}

Given its ease of use and adoption for data science applications, [Python](https://www.python.org/) support is imperative to increase adoption of your IBM Cloud service.  Supporting Python applications using [Flask](https://github.com/pallets/flask), [Django](https://www.djangoproject.com/), [Jupyter](https://jupyter.org/), and functional programming paradigms introduces special considerations that need to be observed by your SDK.

## Environment support
{: #python-environment-support}

* Your Python SDK should be written to support all [Python >=3.5](https://www.python.org/downloads/) releases.
* Ensure your SDK is compatible with data science usecases, such as [Jupyter Notebooks](https://jupyter.org/).

## Publishing
{: #python-publishing}

All Python SDKs should be publicly available on an [IBM GitHub organization](/docs/sdk-handbook?topic=sdk-handbook-distribution#open-source).  The releases of these SDKs should be published on [PyPI](https://pypi.org/).

Your SDK should follow the [semantic versioning best practices](/docs/sdk-handbook?topic=sdk-handbook-distribution#semantic-versioning).

## Community support
{: #python-community-support}

Allow your users to find answers to their questions.  Users should be able to report problems on GitHub by raising issues on your SDK repository.  Having a public Slack channel is a great way to engage with users who have questions specific to their use cases.


## Style guidelines
{: #python-style-guidelines}

You should follow the [PEP8 style guide for Python](https://www.python.org/dev/peps/pep-0008/), with a few modifications, like four spaces instead of tabs for indentation.

You should use the standard [development tools](/docs/sdk-handbook?topic=sdk-handbook-developer-tools) for Python to check style and code coverage.

### Docstrings
{: #python-docstrings}

All non-trivial methods should have docstrings. Docstrings should follow the [PEP257 guidelines](https://www.python.org/dev/peps/pep-0257/). For more examples, see the [Google style guide regarding docstrings](https://google.github.io/styleguide/pyguide.html#381-docstrings).

## Dependencies
{: #python-dependencies}

Your Python SDK should use synchronous network calls, using a library like [requests](https://pypi.org/project/requests/).

[PyJWT](https://pyjwt.readthedocs.io/en/latest/) is recommended for encoding and decoding JSON web tokens.

Your SDK should use [**logging**](https://docs.python.org/3/library/logging.html) to assist users with low-level debugging.


## Standard features
{: #python-standard-features}

## Authentication
{: #python-authentication}

You are not required to use a particular library to provide the authentication for your service.

Your SDK must support all of the authentication methods for your service.

## Configuration
{: #python-configuration}

In the interests of making your SDK easy to consume and cloud native, you should provide the ability to read in environment variables.  Abstracting the application logic from the environment logic allows your users to focus on using your service capabilities their applications.

If you build this capability into your SDK, you must document this mechanism clearly with examples.


## Using python-sdk-core

[IBM **python-sdk-core**](https://github.com/IBM/python-sdk-core) provides configuration and authentication support. You can use the existing functionality provided by this dependency in your SDK.


## Documentation
{: #python-documentation}

Your SDK is not useful if your audience cannot understand how to consume it in order to do the basic operations for your service. Your SDK needs to contain the following resources to help your users:

* `README.md`
* [Contributor guidelines](/docs/sdk-handbook?topic=sdk-handbook-documentation#contributor-documentation)
* [API reference documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation#interface-documentation)
* [Sphinx documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation#interface-documentation)
* Code Samples
* [Service documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation)

## Samples
{: #python-samples}

For your Python SDK, you will want some simple code samples and explanations of what each does.  Linking out to the API reference documentation for more advanced use is strongly encouraged.

At minimum, the samples should be included in the `README.md` file. They should communicate how to install the library, and complete the basic operations provided by your API.

The samples should include simple installation and initialization instructions for the popular frameworks and data science tools.  Additional examples should be available in an `/examples` directory for more advanced operations which can be copied and pasted in to user applications.
