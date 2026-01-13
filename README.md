# gifhost

A lightweight repository for hosting GIFs — here I put my hosted GIFs.

This README shows a "CDN link style" approach so you can embed GIFs with CDN-style URLs (recommended for production embedding).

---

## CDN options (recommended)

1. jsDelivr (recommended, fast, globally cached)
- Pattern:
  - Latest (auto): `https://cdn.jsdelivr.net/gh/<user>/<repo>/gifs/<filename>.gif`
  - Pinned to a tag/commit (immutable, recommended for production):  
    `https://cdn.jsdelivr.net/gh/<user>/<repo>@<tag-or-commit-sha>/gifs/<filename>.gif`
- Examples for this repo:
  - Auto/latest:  
    `https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost/gifs/example.gif`
  - Pinned (replace `<sha>` with actual commit SHA):  
    `https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost@<sha>/gifs/example.gif`

Notes:
- Pinning to a commit SHA or tag gives an immutable URL (safe for caching and long-lived embeds).
- Leaving version out uses the latest build and may be updated when the repo changes — not ideal for permanent embeds.

2. raw.githack.com (simple, mirrors raw GitHub content)
- Pattern:
  `https://raw.githack.com/<user>/<repo>/<branch>/gifs/<filename>.gif`
- Example:
  `https://raw.githack.com/ratul-rahman/gifhost/main/gifs/example.gif`

Notes:
- Good for quick previews and stable raw file hosting, but jsDelivr is generally faster & has better CDN caching.

3. raw.githubusercontent.com (direct raw GitHub URL — not a CDN)
- Pattern:
  `https://raw.githubusercontent.com/<user>/<repo>/<branch>/gifs/<filename>.gif`
- Example:
  `https://raw.githubusercontent.com/ratul-rahman/gifhost/main/gifs/example.gif`

Notes:
- This is GitHub's raw file host. Use jsDelivr for CDN features and global caching.

---

## How to embed

Markdown:
```markdown
![my gif](https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost/gifs/example.gif)
```

HTML:
```html
<img src="https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost@git-sha/gifs/example.gif" alt="example gif" />
```

CSS background:
```css
.element {
  background-image: url("https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost/gifs/example.gif");
}
```

Responsive <picture> (serve GIF fallback or alternatives):
```html
<picture>
  <source srcset="https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost/gifs/example.avif" type="image/avif">
  <img src="https://cdn.jsdelivr.net/gh/ratul-rahman/gifhost/gifs/example.gif" alt="example">
</picture>
```

---

## Recommendations & best practices

- Use jsDelivr pinned URLs (tag or commit SHA) for production embeds to avoid unexpected changes and to take full advantage of CDN caching.
- Keep file sizes small — optimize GIFs (or consider converting to WebP/AVIF for smaller file size and provide GIF as fallback).
- Name files clearly and use lowercase with hyphens, e.g. `happy-dance.gif`.
- If you update a GIF and want consumers to get the new version immediately, publish a new tag or reference the new commit SHA in the CDN URL.
- Respect copyright — only host GIFs you have the right to publish.

---

## Repository structure

- /gifs/ — store your GIF files here
- README.md — this file
- LICENSE — optional (add if you want to set reuse terms)

---

## Next steps I can help with
- Add the `gifs/` folder and example GIF(s) to the repo and commit a pinned URL example.
- Create a small script or badge that lists available GIFs and their CDN URLs.
- Help optimize GIFs or generate WebP/AVIF fallbacks.

If you'd like, I can update the README in the repository with these CDN examples and create an initial `gifs/` folder — tell me whether you want me to commit the changes (and whether to pin example links to `main` or to a specific commit/tag).
