# dispatcher-action
Makes a repository dispatch API call, but includes a link back to the calling workflow so that the dispatched flow
knows _who_ dispatched it - this reduces the number of usable `client_payload` items by 1

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|     INPUT      |  TYPE  | REQUIRED |           DEFAULT            |                                               DESCRIPTION                                               |
|----------------|--------|----------|------------------------------|---------------------------------------------------------------------------------------------------------|
| client-payload | string |  false   |            `"{}"`            | JSON payload for the `repository_dispatch`<br>event (key `dispatched_by` is upserted<br>by this action) |
|   event-type   | string |   true   |                              |                     The `repository_dispatch` event name (also<br>known as `type`)                      |
|   repository   | string |  false   | `"${{ github.repository }}"` |                       The full name of the<br>repository to send the dispatch<br>                       |
|     token      | string |  false   |   `"${{ github.token }}"`    |                              Token with access to the<br>target repository                              |

<!-- AUTO-DOC-INPUT:END -->
