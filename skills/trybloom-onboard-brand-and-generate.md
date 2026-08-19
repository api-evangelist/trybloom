---
name: Onboard a brand and generate an on-brand image
description: >-
  Onboard a brand into Bloom from a website or Instagram URL, wait for analysis
  to finish, then generate an on-brand image and retrieve the result.
api: openapi/_original/trybloom-api-openapi.json
operations: [brands.create, brands.get, images.generate, images.get, credits.get]
generated: '2026-07-21'
method: generated
---

# Onboard a brand and generate an on-brand image

Base URL `https://www.trybloom.ai/api/v1`. Authenticate every call with
`x-api-key: bloom_sk_...` (or `Authorization: Bearer`) — see
`../authentication/trybloom-authentication.yml`.

## Steps

1. **Create the brand** — `brands.create` (`POST /brands`) with
   `{"url": "https://acme.com"}` (a website or Instagram profile URL).
   Returns `202` with `data.id` and `status: "analyzing"`; crawling and
   visual-DNA analysis run in the background. `collectImages: false` skips
   only library collection, not analysis.
2. **Wait for readiness** — `brands.get` (`GET /brands/{id}?wait=true`)
   holds the connection until `ready`, `logo_required`, or `failed`. A
   timeout returns the current `analyzing` resource — call it again.
   - `logo_required`: supply a logo via `brands.updateLogo` (`PUT /brands/{id}/logo`).
   - `failed`: branch on `failure.code` (`INVALID_URL`, `SCRAPE_FAILED`,
     `INSTAGRAM_FETCH_FAILED`, `INTERNAL_ERROR`, `VISUAL_DNA_FAILED`) and
     retry with a new `brands.create`.
3. **Generate** — `images.generate` (`POST /images/generations`) with
   `{"brandSessionId": "<brand id>", "prompt": "..."}`. Optional:
   `aspectRatio` (`1:1`…`21:9`), `imageSize` (`2K` = 1 credit, `4K` = 2),
   `model` (`fast`/`standard`/`pro`), `variantCount` (1–5),
   `referenceImageIds`. Returns `202` with `data.imageIds`.
   A `409 BRAND_NOT_READY` means step 2 has not completed.
4. **Retrieve** — `images.get` (`GET /images/{id}?wait=true`) long-polls to a
   terminal state; `data.imageUrl` carries the finished image.
5. **Check credits (optional)** — `credits.get` (`GET /credits`); a `402`
   with `INSUFFICIENT_CREDITS` or `PAYMENT_REQUIRED` includes a
   `data.action_url` to resolve.

## Rules

- Success envelope is `{"data": ...}`; errors are
  `{"error": {code, status, message}}` — branch on `code`
  (`../errors/trybloom-problem-types.yml`).
- 120 requests/minute per key; back off on `429 TOO_MANY_REQUESTS`.
- No idempotency keys: never blind-retry a `POST` that may have been
  accepted — check state with `brands.get` / `images.get` first.
