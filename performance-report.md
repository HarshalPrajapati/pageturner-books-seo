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
| Largest Contentful Paint (LCP) | Not captured | 0.8 s | Reduced image transfer and deferred below-fold media can improve LCP. |
| Interaction to Next Paint (INP) | Not captured | No field data | The site is newly deployed, so PageSpeed does not yet have Chrome UX Report data for INP. |
| Cumulative Layout Shift (CLS) | Not captured | 0 | Explicit image dimensions should reduce CLS. |

### After-test result

Google PageSpeed Insights mobile laboratory test, captured 19 August 2026, reported: Performance **100**, Accessibility **100**, Best Practices **96**, and SEO **100**. The report included LCP of **0.8 s**, CLS of **0**, and no real-user field data. The image-delivery audit estimated a potential saving of 210 KiB; the page already uses WebP delivery and lazy loading for below-the-fold images.

## Validation checklist

- Paste the complete `bookstore.html` into validator.schema.org and save a screenshot.
- Validate `sitemap.xml` and run PageSpeed Insights using the deployed GitHub Pages URL.
