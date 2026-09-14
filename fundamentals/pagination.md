---

copyright:
  years: 2019, 2026
lastupdated: "2026-09-14"

keywords: sdk, pagination, pagination helpers

subcollection: sdk-handbook

---

{{site.data.keyword.attribute-definition-list}}

# Pagination
{: #pagination}

These guidelines define how an SDK must support pagination for API operations that return paginated results.
{: shortdesc}

## Support for pagination features in the API
{: #pagination-api}

The SDK MUST support pagination for any methods whose underlying API implements pagination.

## Pagination helpers
{: #pagination-helpers}

The SDK MAY offer pagination "helper" methods that ease the burden of retrieving paginated lists of resources.
The network-call complexity of these methods MUST be clear and under the control of the user.
