# Thorvaldsson Games — Website
Source for the GitHub Pages portfolio site at **thorvaldssongames.com**

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