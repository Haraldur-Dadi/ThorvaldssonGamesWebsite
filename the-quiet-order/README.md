# The Quiet Order — WebGL Build

Drop your Unity WebGL build output here.

## Expected structure

After building from Unity (Build Settings → WebGL), copy the contents of the
build output folder so this directory looks like:

```
the-quiet-order/
├── index.html          ← Unity's generated loader page
├── Build/
│   ├── *.loader.js
│   ├── *.data.gz
│   ├── *.framework.js.gz
│   └── *.wasm.gz
├── TemplateData/       ← Unity's CSS/favicon assets
│   └── ...
└── README.md           ← this file
```

## Unity build settings checklist

- Platform: WebGL
- Compression Format: Gzip (recommended for GitHub Pages)
- Publishing Settings → Decompression Fallback: **enabled** (required when
  the server doesn't set the correct Content-Encoding headers — GitHub Pages
  falls into this category)
- Player Settings → Resolution and Presentation → WebGL Template: Default or
  your custom template

## Notes

- The `.nojekyll` file at the repo root tells GitHub Pages to serve files as-is
  without Jekyll processing, which is required for Unity's compressed builds.
- If you see a blank screen or network errors after deploy, check the browser
  console — the most common cause is missing `.nojekyll` or Decompression
  Fallback not being enabled.
