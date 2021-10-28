---

copyright:
  years: 2019, 2021
lastupdated: "2021-10-28"

subcollection: sdk-handbook

---

# Naming
{: #naming}

## Consistency of names
{: #naming-consistency}

The names of classes, methods, properties, and parameters MUST be consistent across all SDKs for a service
and SHOULD be consistent with the names in the underlying API.

## Package names
{: #naming-pkgnames}

The name of the SDK's installable package MUST be descriptive of the set of services that are supported by the SDK
and be consistent across all SDKs, to the extent allowed by the [package managers](/docs/sdk-handbook?topic=sdk-handbook-devtools#devtools-pkg-mgmt).

For IBM Cloud SDKs, the SDK package name SHOULD be directly derived from the `category` of the SDK services
as displayed in the [IBM Cloud API & SDK reference library](https://cloud.ibm.com/docs?tab=api-docs).
Under this pattern, each service SHOULD have a corresponding module that contains its API operations.
For example, the [Platform Services Node SDK](https://github.com/IBM/platform-services-node-sdk) includes the services found in the [Platform Services](https://cloud.ibm.com/docs?tab=api-docs&category=platform_services) category as separate modules, such as the [Global Search](https://cloud.ibm.com/apidocs/search?code=node) service that can be imported into your Node.js application using an import path of `@ibm-cloud/platform-services/global-search/v2`.  These multi-service SDKs have the same structure as a single-service SDK, but lower the barrier to entry for user adoption and exploration of other services while potentially providing shared utilities across similar services.

## Classes, structs, and types
{: #naming-classnames}

Names for classes, structs, or types SHOULD be simple, descriptive, and meaningful to developers.
Such names should generally be nouns or noun phrases.

For example:
- Use `Trait` rather than `TraitTreeNode`
- Use `Classifier` rather than `GetClassifiersTopLevelBrief`

## Methods
{: #naming-methods}

Names for methods or functions SHOULD follow the convention of `<verb>_<noun>`, where the noun is typically the resource type[^method-naming].

The following table describes the standard naming conventions for methods and functions that map to operations on resources in a resource-oriented API.

| Verb              | Return type         | Maps to operation          |  Comments  |
| ----------------- | ------------------- | -------------------------- | --- |
| `list`            | Resource collection | `GET` to the `/resources` endpoint | Return a possibly paginated list of resources. |
| `create` or `add` | Resource            | `POST` to the `/resources` endpoint | Create new resource. |
| `get`             | Resource            | `GET` to the `/resources/{id}` endpoint | Return the resource with identifier `{id}`. |
| `update`          | Resource            | `POST` or `PATCH` to the `/resources/{id}` endpoint | Partial or selective update an existing resource. |
| `replace`         | Resource            | `PUT` to the `/resources/{id}` endpoint | Replace an existing resource. |
| `delete`          | (None)              | `DELETE` to the `/resources/{id}` endpoint | Delete the resource with identifier `{id}`. |
| `set`             | Resource            | `PUT` to the `/resources/{id}` endpoint | Create a new resource or update the existing resource with identifier `{id}`. |
| `check`           | Resource            | `GET` to the `/resources/{id}` endpoint | Success response if resource exists, else error. |
{: caption="Table 1. Naming conventions for methods and functions" caption-side="bottom"}

Operations that do not fit into one of the standard verb forms SHOULD use an "action" verb form,
such as "translate" or "synthesize", and MAY omit the noun where it is implied or otherwise unnecessary.

Action methods generally map to either a `POST` or a `GET` operation, where `GET` is only permitted if the action is safe and idempotent.

## Namespaces
{: #naming-namespaces}

All classes and methods of the SDK SHOULD be encapsulated in a namespace whenever possible in the language.
Using namespaces minimizes the potential for naming conflicts with other packages and provides structure to the reference documentation.


[^method-naming]: Consistent with [Microsoft](https://azure.github.io/azure-sdk/general_design.html#client-interface) and [Google](https://cloud.google.com/apis/design/standard_methods) guidelines.
