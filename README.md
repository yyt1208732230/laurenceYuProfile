# laurenceYuProfile

Static personal profile site for GitHub Pages.

## Edit content

Most profile content lives in `content.json`. Update that file to revise publications, awards, projects, recent activities, profile links and photo wall items.

Selected text fields support simple inline HTML, including `<a href="">`, `<br>`, `<strong>`, `<em>`, `<b>`, `<i>`, `<small>`, `<sup>`, `<sub>`, `<code>` and `<span>`. This is useful for adding links inside descriptions without editing `index.html`.

## Image Sizes

Recommended replacement assets:

- Hero image: `1080 x 1920 px`, `9:16`, portrait. Keep the subject centred with enough breathing room around the edges. The page caps this image so it reads as a framed profile/instant-camera photo rather than a full-screen banner.
- Profile portrait: `1200 x 1500 px`, `4:5`, face/upper body centred, JPG/WebP.
- Research outcome teaser figures: `1600 x 1000 px`, `16:10`. Use clean paper-style figures, system diagrams, study setup photos, charts, or cropped screenshots. Add the path as `teaser` inside each item in `content.json` under `publications`.
- Project teaser figures: `2100 x 900 px`, `21:9`. Use wider scene photos, simulator/test-track/on-road setup shots, interface screenshots, or project workflow images. Add the path as `teaser` inside each item in `content.json` under `projects`.
- Experience logos: `512 x 512 px`, `1:1`, transparent PNG or square WebP preferred. Add the path as `logo` inside each item in `content.json` under `experience`.
- Photo wall lead image: `2400 x 1600 px`, `3:2` or `16:10`.
- Photo wall secondary images: `1600 x 1200 px`, `4:3`.

The hero uses a fixed portrait frame. Replace `profile.heroImage` and `profile.portrait` in `content.json` after adding new files to `images/`.

Example:

```json
{
  "title": "Research paper title",
  "teaser": "images/research/example-paper-teaser.webp",
  "teaserAlt": "Short description of the teaser figure"
}
```

## Run locally

Because `index.html` fetches `content.json`, serve the folder rather than opening the HTML file directly:

```powershell
python -m http.server 8000
```

Then visit `http://127.0.0.1:8000/`.

## Deploy on GitHub Pages

Push the repository to GitHub, then enable Pages from the repository settings:

- Source: deploy from branch
- Branch: `main`
- Folder: `/root`

The site has no build step and no external runtime dependencies.
