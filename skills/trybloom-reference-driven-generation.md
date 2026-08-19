---
name: Reference-driven generation from the brand library
description: >-
  Upload reference images or find them in the brand's library with semantic
  search, then generate an on-brand image steered by those references.
api: openapi/_original/trybloom-api-openapi.json
operations: [images.upload, images.search, images.generate, images.get]
generated: '2026-07-21'
method: generated
---

# Reference-driven generation from the brand library

A couple of good references measurably improve composition and styling.
References come from two places: images you upload, and the brand's library
(images `uploaded` by the user or `scraped` during onboarding).

## Steps

1. **Upload a reference (optional)** — `images.upload`
   (`POST /images/uploads`) with a remote URL, or `images.uploadFile`
   (`POST /images/uploads/file`, multipart) for local bytes. Returns an
   image id usable as a reference or edit subject. Watch for `400` codes
   `DOWNLOAD_FAILED`, `FILE_TOO_LARGE`, `IMAGE_TOO_SMALL`,
   `UNSUPPORTED_FORMAT`.
2. **Search the library** — `images.search` (`POST /images/search`) with a
   concept description; vector-ranked, nearest-first, over library images
   only (generated images are excluded). Paginate with `cursor` from the
   previous response. No matches is a valid result — generation works
   without references.
3. **Generate with references** — `images.generate`
   (`POST /images/generations`) passing `referenceImageIds` with the chosen
   ids alongside `brandSessionId` and `prompt`.
   `400 REFERENCE_LIMIT_EXCEEDED` means too many references;
   `404 REFERENCE_IMAGE_NOT_FOUND` means a bad id.
4. **Retrieve** — `images.get` (`GET /images/{id}?wait=true`) until
   `completed`; `data.imageUrl` is the result.

## Rules

- Envelope and error discipline as in `../conventions/trybloom-conventions.yml`:
  branch on `error.code`, respect `429 TOO_MANY_REQUESTS` (120 req/min/key).
- Spend words on the subject, not the brand — palette, type, and aesthetic
  come from the brand's visual DNA.
