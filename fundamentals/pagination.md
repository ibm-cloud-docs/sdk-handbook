---

copyright:
  years: 2019, 2021
lastupdated: "2021-10-27"

subcollection: sdk-handbook

---
# Pagination
{: #pagination}

## Support for pagination features in the API
{: #pagination-api}

The SDK MUST support pagination for any methods whose underlying API implements pagination.

## Pagination helpers
{: #pagination-helpers}

The SDK MAY offer pagination "helper" methods that ease the burden of retrieving paginated lists of resources.
The network-call complexity of these methods MUST be clear and under the control of the user.
