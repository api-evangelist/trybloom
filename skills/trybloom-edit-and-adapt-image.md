---
name: Edit and adapt an image
description: >-
  Edit an existing Bloom image, resize it for another channel, remove its
  background, or vectorize it to SVG — each producing a new image to poll.
api: openapi/trybloom-api-openapi.json
operations: [images.edit, images.resize, images.removeBackground, images.vectorize, images.get, images.list]
generated: '2026-07-21'
method: generated
---

# Edit and adapt an image

All four adaptations are asynchronous: they return `202` with a **new** image
id immediately; retrieve the result with `images.get`
(`GET /images/{id}?wait=true`). The source image must be in a usable state —
generated images must be `completed`; uploaded/scraped images work as-is.

## Steps

1. **Find the image** — `images.list` (`GET /images`) with cursor pagination
   (`cursor`, `limit`, filter by `brandSessionId`, `status`, `actionType`),
   or use the id you already hold.
2. **Pick the adaptation**:
   - **Edit** — `images.edit` (`POST /images/{id}/edit`): prompt describes
     the change; aspect ratio is locked to the original; optional
     `referenceImageIds` for context.
   - **Resize** — `images.resize` (`POST /images/{id}/resize`) to a new
     aspect ratio; `400 SAME_ASPECT_RATIO` if it matches the original.
   - **Remove background** — `images.removeBackground`
     (`POST /images/{id}/remove-background`): returns a transparent PNG,
     typically under 10 seconds.
   - **Vectorize** — `images.vectorize` (`POST /images/{id}/vectorize`):
     raster → SVG; best for logos/icons/flat artwork, poor for photos.
3. **Retrieve** — `images.get` with `wait=true` until `completed` or
   `failed` (`failureReason: content_safety` means the prompt was blocked —
   rephrase or switch model tier).

## Rules

- Expect state-precondition errors as `400` codes: `IMAGE_NOT_COMPLETED`,
  `IMAGE_NOT_RESIZABLE`, `IMAGE_NOT_VECTORIZABLE`,
  `IMAGE_NOT_REMOVABLE_BACKGROUND` (`../errors/trybloom-problem-types.yml`).
- Each adaptation debits credits like a generation (2K = 1, 4K = 2).
- Batch retrieval: `images.list` accepts `ids=...&wait=true` to hold until
  every referenced image is terminal.
