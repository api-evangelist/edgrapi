---
name: edgrapi-webhook-create-test-delete
description: Create a webhook, send a test delivery, view recent deliveries, and then delete the webhook.
api: openapi/edgrapi-openapi.json
operations:
- webhook_create_v1_webhooks_post
- webhook_test_v1_webhooks__wid__test_post
- webhook_deliveries_v1_webhooks__wid__deliveries_get
- webhook_delete_v1_webhooks__wid__delete
generated: '2026-10-16'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/edgrapi-openapi.json ; every operationId checked against the contract
---

# edgrapi-webhook-create-test-delete

Create a webhook, send a test delivery, view recent deliveries, and then delete the webhook.

## Steps

1. 1. `webhook_create_v1_webhooks_post` – send required webhook creation fields in the request body; response includes the webhook ID (`wid`).
2. 2. `webhook_test_v1_webhooks__wid__test_post` – use the `wid` from step 1 in the path; no additional body fields required.
3. 3. `webhook_deliveries_v1_webhooks__wid__deliveries_get` – retrieve recent delivery attempts for the `wid`; supports optional query parameters for filtering.
4. 4. `webhook_delete_v1_webhooks__wid__delete` – delete the webhook identified by `wid`.

## Rules

- Rate limiting: The response includes header `X-RateLimit-Limit: 100`; exceeding the limit returns HTTP 429.
