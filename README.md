# thecodejedi.github.io

Personal blog of Markus Hoffmann ([oberfreak](https://invent.kde.org/oberfreak) on KDE Invent), aggregated on [Planet KDE](https://planet.kde.org).

Jekyll blog hosted on GitHub Pages.

- Site: https://thecodejedi.github.io
- RSS feed (used by Planet KDE): https://thecodejedi.github.io/feed.xml

## Setup (one-time)

1. Enable GitHub Pages: on this repository, go to **Settings > Pages > Build and deployment > Source: "Deploy from a branch"**, then Branch: `main`, Folder: `/ (root)` > **Save**.
2. Wait for the build to finish (see the **Actions** tab). The site goes live at https://thecodejedi.github.io

## Add the screenshots

Copy the three screenshots into `images/` using the exact file names listed in `images/README.md`, then commit and push. The first post references them.

## Write a new post

1. Add a Markdown file to `_posts/` named `YYYY-MM-DD-short-title.md`:

   ```
   ---
   layout: post
   title: "Your post title"
   date: YYYY-MM-DD
   ---

   Your text here. Images live in `images/` and are referenced as `/images/name.png`.
   ```

2. Commit and push to `main`. GitHub Pages rebuilds automatically.

## Preview locally

```
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000
