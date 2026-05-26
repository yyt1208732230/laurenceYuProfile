# laurenceYuProfile

Static personal profile site for GitHub Pages.

## Edit content

Most profile content lives in `content.json`. Update that file to revise publications, awards, projects, recent activities, profile links and photo wall items.

Selected text fields support simple inline HTML, including `<a href="">`, `<br>`, `<strong>`, `<em>`, `<b>`, `<i>`, `<small>`, `<sup>`, `<sub>`, `<code>` and `<span>`. This is useful for adding links inside descriptions without editing `index.html`.

Items that appear in `cv.html` support `showInCV`. It defaults to `true`; set it to `false` to hide only from the generated CV page:

```json
{
  "name": "Python",
  "showInCV": false
}
```

Supported sections include `publications`, `experience`, `education`, `awards`, `skills`, and `certifications`.

## Image Sizes

Recommended replacement assets:

- Hero image: `1080 x 1920 px`, `9:16`, portrait. Keep the subject centred with enough breathing room around the edges. The page caps this image so it reads as a framed profile/instant-camera photo rather than a full-screen banner.
- Profile portrait: `1200 x 1500 px`, `4:5`, face/upper body centred, JPG/WebP.
- Research outcome teaser figures: `1600 x 1000 px`, `16:10`. Use clean paper-style figures, system diagrams, study setup photos, charts, or cropped screenshots. Add the path as `teaser` inside each item in `content.json` under `publications`.
- Project teaser figures: `2100 x 900 px`, `21:9`. Use wider scene photos, simulator/test-track/on-road setup shots, interface screenshots, or project workflow images. Add the path as `teaser` inside each item in `content.json` under `projects`.
- Experience logos: `512 x 512 px`, `1:1`, transparent PNG or square WebP preferred. Add the path as `logo` inside each item in `content.json` under `experience`.
- Experience logo links: add `url` beside `logo`. When `url` is present, clicking the logo opens that organisation/project page in a new tab.
- Photo wall lead image: `2400 x 1600 px`, `3:2` or `16:10`.
- Photo wall secondary images: `1600 x 1200 px`, `4:3`.

The hero uses a fixed portrait frame. Replace `profile.heroImage` and `profile.portrait` in `content.json` after adding new files to `images/`.

Hero video is optional. Set `profile.heroVideo` to an MP4 path such as `images/life-on-car-fix.mp4`. The hero image remains the fallback poster if the video cannot load.

Example:

```json
{
  "title": "Research paper title",
  "teaser": "images/research/example-paper-teaser.webp",
  "teaserAlt": "Short description of the teaser figure"
}
```

Experience logo example:

```json
{
  "role": "PhD Candidate",
  "organisation": "AVR3 / CARRS-Q, Queensland University of Technology",
  "period": "Feb 2024 - Present",
  "description": "Researching advanced HMI for automated vehicles.",
  "logo": "images/logos/qut.png",
  "url": "https://www.qut.edu.au/"
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
