# Performance optimization report

## Changes made

- Converted external image delivery requests to WebP (`fm=webp`) with quality 70 and width limits.
- Added `loading="lazy"` and `decoding="async"` to non-critical book images.
- Added explicit image dimensions to prevent layout shifts (CLS).
- Used a flexible layout that avoids oversized assets on small screens.
- Set the video to `preload="metadata"`, so the video file is not fully downloaded before a visitor plays it.

## PageSpeed comparison

Run PageSpeed Insights twice against a deployed URL: once before these changes and once afterward. Record the field/lab values below and attach the two result screenshots required by the lab.

| Metric | Before | After | Expected effect |
| --- | ---: | ---: | --- |
| Largest Contentful Paint (LCP) | — | — | Reduced image transfer and deferred below-fold media can improve LCP. |
| Interaction to Next Paint (INP) | — | — | The page has no heavy client-side JavaScript. |
| Cumulative Layout Shift (CLS) | — | — | Explicit image dimensions should reduce CLS. |

## Validation checklist

- Paste the complete `bookstore.html` into validator.schema.org and save a screenshot.
- Deploy the files before validating `sitemap.xml` and before running PageSpeed Insights; `.example` URLs in the source must be replaced with the actual deployed domain.
