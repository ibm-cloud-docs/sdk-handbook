---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---
# Pagination

## Support for pagination features in the API

The SDK MUST support pagination for any methods whose underlying API implements pagination.

## Pagination helpers

The SDK MAY offer pagination "helper" methods that ease the burden of retrieving paginated lists of resources.
The network-call complexity of these methods MUST be clear and under the control of the user.
