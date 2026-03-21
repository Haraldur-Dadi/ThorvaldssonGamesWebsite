# Thorvaldsson Games — Website

Source for the GitHub Pages portfolio site at **halli.games** (or
`<your-username>.github.io/<repo-name>` until a custom domain is configured).

## Repo structure

```
/
├── index.html              ← Landing page listing all games
├── .nojekyll               ← Disables Jekyll; required for Unity WebGL builds
├── README.md               ← This file
└── the-quiet-order/
    ├── README.md           ← Instructions for dropping in the WebGL build
    └── (Unity WebGL build files go here)
```

## Adding a new game

1. Create a folder for the game, e.g. `my-new-game/`.
2. Drop your Unity WebGL build output into that folder.
3. Add a card for it in `index.html` — copy the existing `.game-card` block
   and update the title, description, badge, and `href`.
4. Commit and push to `main`.

## Deploying a Unity WebGL build

1. In Unity: **File → Build Settings → WebGL → Build**.
2. Copy the entire build output folder contents into the game's subfolder
   (e.g. `the-quiet-order/`). You want `index.html`, `Build/`, and
   `TemplateData/` to live directly inside that folder.
3. Make sure **Decompression Fallback** is enabled in Publishing Settings
   (required for GitHub Pages which doesn't set `Content-Encoding` headers).
4. `git add the-quiet-order/ && git commit -m "deploy: update quiet order build" && git push`

GitHub Pages will serve the update within ~1 minute.

## Enabling GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Source: **Deploy from a branch**.
4. Branch: `main`, folder: `/ (root)`.
5. Save. GitHub will provide a URL like `https://<username>.github.io/<repo>/`.

## Custom domain (halli.games)

1. In your DNS provider, add:
   ```
   Type   Name    Value
   A      @       185.199.108.153
   A      @       185.199.109.153
   A      @       185.199.110.153
   A      @       185.199.111.153
   CNAME  www     <username>.github.io.
   ```
2. In GitHub: **Settings → Pages → Custom domain**, enter `halli.games`, save.
3. GitHub will auto-provision an HTTPS certificate (takes a few minutes).
4. Check **Enforce HTTPS** once the certificate is ready.
5. A `CNAME` file will be auto-created in the repo root — don't delete it.
