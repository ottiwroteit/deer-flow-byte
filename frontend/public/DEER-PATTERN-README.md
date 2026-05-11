# Deer Pattern Background Asset

The DeerFlow UI references `/deer-pattern.jpg` (this folder) as the background
texture for the sidebar and main app surface. **Until you drop a real image
here, the background falls back to a flat cream color** — the layout still
works, it's just not patterned yet.

## How to source the image

The Magnific URLs in the original spec are stock-photo *preview pages*, not
direct image files, and Magnific blocks hotlinking. You need to download or
license a real image and save it as `deer-pattern.jpg` in this folder.

Recommended sources:

- **Magnific** (paid): purchase the license, download the JPG, save here.
- **Unsplash / Pexels** (free): search "deer fur texture" or "fawn skin
  pattern". Most are free for commercial use with attribution.
- **Adobe Stock / Shutterstock** (paid): higher quality, more variety.
- **AI generated**: prompt Midjourney / DALL·E / Imagen for a tileable
  deer-fur pattern in cream + tan.

## Image guidelines

- **Format:** JPG (smallest file size for a photographic texture).
- **Dimensions:** at least 2000×2000 px so it stays sharp on retina
  displays at large window sizes.
- **Color:** ideally cream / tan / soft brown — the CSS overlay assumes a
  warm palette. Cool-blue or grayscale images will fight the cream
  overlay (`rgba(250, 249, 246, ...)`) and look muddy.
- **Tileable / continuous:** since the CSS uses `background-size: cover`,
  the image is stretched and centered — non-tileable photos work fine.
- **File size:** keep under 500 KB if possible (use `imageoptim` or
  squoosh.app to compress before saving).

## Filename

Save as exactly: `deer-pattern.jpg`

If you prefer a different filename, update the two `url('/deer-pattern.jpg')`
references in `frontend/src/styles/globals.css` accordingly.

## Adjusting the overlay opacity

The pattern is overlaid with a 82% opaque cream wash on the sidebar and 90%
on the main area. If the pattern feels too strong or too subtle, edit the
`rgba(250, 249, 246, X)` alpha values in `globals.css`:

- More pattern visible: lower the alpha (e.g. `0.7`)
- Less pattern visible: raise the alpha (e.g. `0.95`)

Dark mode uses `rgba(36, 35, 35, X)` — the same logic applies.
