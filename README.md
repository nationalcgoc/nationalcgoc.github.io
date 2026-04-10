# DAFCGOC Website

Public website for the Department of the Air Force Company Grade Officers' Council.

**Live site**: [dafcgoc.org](https://dafcgoc.org)

## Stack

- **HTML/CSS/JS** — static site, no build system or framework
- **Leaflet.js** 1.9.4 — interactive council locator map with GeoJSON data
- **Font Awesome** 5.15.1 — icons (via CDN)
- **Google Fonts** — Open Sans (via CDN), Raleway and Merriweather (self-hosted)
- **GitHub Pages** — hosting and deployment

No `package.json`, no bundler, no transpiler. Edit files directly and push.

## Project Structure

```
├── index.html                  # Homepage
├── pages/
│   ├── leadership.html         # Leadership team directory
│   ├── councils.html           # Interactive map of all councils
│   ├── award-winners.html      # Awards and recognition
│   ├── resources.html          # Documents and training materials
│   ├── donate.html             # Donation page (Zeffy embed)
│   ├── store.html              # Merchandise (Zeffy embed)
│   ├── moaa.html               # MOAA partnership
│   └── defo.html               # DEFO program
├── css/
│   ├── base.css                # Normalize/reset
│   ├── main.css                # All custom styles
│   ├── fonts.css               # @font-face declarations
│   └── vendor.min.css          # Magnific Popup + vendor CSS
├── js/
│   ├── main.js                 # Navigation, modals, preloader
│   ├── map-functionality.js    # Leaflet map init + GeoJSON loading
│   └── installations.geojson   # Council location data
├── assets/
│   ├── images/team/            # Leadership headshots
│   ├── images/portfolio/       # Homepage gallery photos
│   ├── logos/                   # DAFCGOC, MOAA, DEFO logos
│   └── products/               # Downloadable docs (templates, briefs, etc.)
├── fonts/                      # Raleway + Merriweather WOFF/TTF
├── CNAME                       # Custom domain: dafcgoc.org
└── sitemap.xml                 # SEO sitemap
```

## Getting Started

1. **Clone the dev repo**:
   ```bash
   git clone https://github.com/daf-cgoc-2025/nationalcgoc.github.io.git
   cd nationalcgoc.github.io
   ```

2. **Set up remotes** (if you need access to prod):
   ```bash
   git remote add upstream https://github.com/nationalcgoc/nationalcgoc.github.io.git
   ```

3. **Run locally** — open `index.html` in a browser, or use any local server:
   ```bash
   python3 -m http.server 8000
   # then visit http://localhost:8000
   ```

## Git Workflow

```
feature branch → dev master → PR to prod master
```

| Repo | Role | URL |
|------|------|-----|
| `daf-cgoc-2025/nationalcgoc.github.io` | **Dev / staging** | Push here for testing |
| `nationalcgoc/nationalcgoc.github.io` | **Production** | Deploy via cross-fork PR only |

1. Create a feature branch off dev `master`
2. Make changes, commit, push to `origin` (dev repo)
3. Merge to dev `master` for user acceptance testing
4. When approved, open a PR from dev → prod (`nationalcgoc/nationalcgoc.github.io`)

**Never push directly to the production repo.**

## Adding Council Locations

Council markers are driven by `js/installations.geojson`. Each feature has properties for base name, location, region, president, VP, and contact links. Add a new entry and push — the map picks it up automatically.

## Domain and Email

- **Domain**: `dafcgoc.org` (configured via Google Domains with permanent redirect + SSL)
- **Email**: `@dafcgoc.org` addresses forward to personal inboxes (receive-only; cannot send from the domain)

## Adding Contributors

Repo access is managed through GitHub settings:
- Dev repo: [daf-cgoc-2025 settings](https://github.com/daf-cgoc-2025/nationalcgoc.github.io/settings/access)
- Prod repo: [nationalcgoc settings](https://github.com/nationalcgoc/nationalcgoc.github.io/settings/access)

## Credits

Originally built and designed by Dannika Thompson.
