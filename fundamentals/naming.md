---

copyright:
  years: 2019
lastupdated: "2020-01-24"

subcollection: sdk-handbook

---

# Naming

## Consistency of names

The names of classes, methods, properties, and parameters MUST be consistent across all SDKs for a service
and SHOULD be consistent with the names in the underlying API.

## Package names

The name of the SDK's installable package MUST be descriptive of the set of services that are supported by the SDK
and be consistent across all SDKs, to the extent allowed by the [package managers](/docs/sdk-handbook/devtools.html#package-management).

For IBM Cloud SDKs, the SDK package name SHOULD be directly derived from the "Category" of the SDK services
as displayed in the [IBM Cloud catalog](https://cloud.ibm.com/catalog).
Under this pattern, each service SHOULD have a corresponding module that contains its API operations.
For example, the Swift [Watson SDK](https://github.com/watson-developer-cloud/swift-sdk) includes all Watson services as different modules, such as [`Sources/VisualRecognitionV3`](https://github.com/watson-developer-cloud/swift-sdk/tree/master/Source/VisualRecognitionV3).
These multi-service SDKs have the same structure as a single service SDK, but lower the barrier to entry for user adoption and exploration of other services while potentially providing shared utilities across similar services.

## Classes, structs, and types

Names for classes, structs, or types SHOULD be simple, descriptive, and meaningful to developers.
Such names should generally be nouns or noun phrases.

For example:
- Use `Trait` rather than `TraitTreeNode`
- Use `Classifier` rather than `GetClassifiersTopLevelBrief`

## Methods

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

Operations that do not fit into one of the standard verb forms SHOULD use an "action" verb form,
such as "translate" or "synthesize", and MAY omit the noun where it is implied or otherwise unnecessary.

Action methods generally map to either a `POST` or a `GET` operation, where `GET` is only permitted if the action is safe and idempotent.

## Namespaces

All classes and methods of the SDK SHOULD be encapsulated in a namespace whenever possible in the language.
Using namespaces minimizes the potential for naming conflicts with other packages and provides structure to the reference documentation.

<!-- --------------------------------------------------------------------- -->

[^method-naming]: Consistent with [Microsoft](https://azure.github.io/azure-sdk/general_design.html#client-interface) and [Google](https://cloud.google.com/apis/design/standard_methods) guidelines.
