# Collection Forge

A single-page tool that lets anyone build an Improved Loading Screens image
Collection and publish it to GitHub, so it streams straight into Darktide.

It is one static file (`index.html`) — no server, no build step, free forever.
It talks only to `api.github.com` from the visitor's own browser using a token
they paste in; nothing is ever sent anywhere else.

## Deploy (one time)

1. Create a new **public** GitHub repo, e.g. `collection-forge`.
2. Add `index.html` to it (it's ~20 KB, so the browser upload is fine).
3. Repo **Settings → Pages → Source: Deploy from a branch → main → /(root) → Save**.
4. After ~1 minute it's live at
   `https://<your-username>.github.io/collection-forge/`.

## How a visitor uses it

1. Click the link on the page to generate a GitHub token (scope `public_repo`
   is pre-selected), copy it, paste it in, press **Establish Link**.
2. Name the Collection, drag in image files.
3. **Forge Collection** — it creates the repo and uploads everything via the
   Git Data API (blobs → tree → commit), which has no upload-size wall.
4. It hands back an `owner/repo` line to paste into the mod's `collection.lua`.

Unofficial fan tool. Not affiliated with Fatshark or Games Workshop.
