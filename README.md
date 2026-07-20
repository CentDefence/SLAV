# Slavic Nation Club | RFL

A single-page website for the Slavic Nation Club Roblox RFL community — dark navy / red / white theme, glassmorphism cards, animated particle background, and a page for every member nation with a searchable, sortable squad table.

## 📁 Structure

```
.
├── index.html         ← the entire site (HTML + CSS + JS in one file)
├── loading-logo.png   ← Slavic ornament emblem, shown on the loading screen
├── rfl-logo.png        ← Real Futbol League badge, shown in the top nav bar and hero
├── favicon.png         ← browser tab icon (cropped from the ornament)
├── .nojekyll            ← tells GitHub Pages to skip Jekyll processing
└── README.md
```

All files sit in the **root** of the repository — this matters for GitHub Pages, don't nest them in a subfolder.

## 🚀 Deploy on GitHub Pages

1. Create a new repository on GitHub and push these files to it (or upload them via "Add file → Upload files").
2. Go to **Settings → Pages**.
3. Under **Source**, choose the `main` branch and `/ (root)` folder, then **Save**.
4. Wait a minute — your site will be live at `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`.

## 🖼️ Replace the logos

Two logos are wired in:

- `loading-logo.png` — the ornament shown while the site loads
- `rfl-logo.png` — the league badge, shown in the top nav bar and centered in the homepage hero

To swap either, just overwrite the file with the same name, or rename your file and update the matching `<img src="...">` in `index.html`.

## 👥 Fill in the squads

All player data lives in one place near the bottom of `index.html`, inside the `COUNTRIES` array:

```js
const COUNTRIES = [
  { code:"pl", flag:"🇵🇱", name:"Poland",
    desc:"Disciplined and <b>tactically sharp</b>...",
    players: [
      { num: 9, name: "Ivan Petrov", pos: "Forward", age: 19, apps: 12, goals: 8 },
      { num: 4, name: "Marek Kowalski", pos: "Defender", age: 21, apps: 10, goals: 1 },
    ]
  },
  ...
];
```

Just add objects to the `players` array for each country — the squad table (with search + sorting) fills itself automatically. Leave `players: []` empty for a country until you're ready to add its roster.

## ✏️ Editing text

- **Hero title / tagline** — in the `<section id="page-home">` block, inside `.hero`.
- **About Club text** — inside `.about-card`.
- **Country descriptions** — the `desc` field per country in the `COUNTRIES` array (use `<b>...</b>` for bold words).

## 🎨 Customizing colors

All colors are CSS variables at the top of the `<style>` block:

```css
--navy-deep:#060a1a;
--navy:#0b1330;
--red:#e0202a;
--red-glow:#ff3c46;
--gold:#c9a24a;
--white:#f2f4fa;
```

Change these and the whole site updates.

## ⚙️ No build step needed

This is a plain static HTML/CSS/JS site — no npm, no build tools. Just open `index.html` in a browser to preview locally, or push to GitHub Pages / Netlify / Vercel as-is.
