# Technical documentation

This guide covers the project from a fresh checkout through local development, content updates, and deployment. The site is a static front end: it uses HTML, CSS, JavaScript, and Vite, with no application server, database, or runtime API.

## 1. Requirements

- Node.js 20.19+ or 22.12+ and npm (the range required by the Vite version in the lockfile).
- VS Code or another editor.
- Git is optional for local use and required for the command-line GitHub workflow below.

## 2. Install and run

Open a terminal in the project root (the folder containing `package.json`):

```sh
npm install
npm run dev
```

Vite prints the local URL in the terminal. Open it in a browser and leave the command running during development. Press `Ctrl+C` to stop it. Changes to HTML, CSS, and JavaScript are served as you save them.

## 3. Available npm commands

| Command | Result |
| --- | --- |
| `npm run dev` | Starts the local Vite development server on `127.0.0.1`. |
| `npm run build` | Creates the production site in `dist/`. |
| `npm run preview` | Serves the most recent `dist/` build locally. Run the build first. |

`package-lock.json` records the dependency versions. Keep it in the repository and use `npm install` after cloning. `node_modules/` and `dist/` are generated locally and are excluded by `.gitignore`.

## 4. How the site is organized

The site has one HTML document with eight views: the archive landing page plus Apollo 11, Kepler / K2, Surveyor 3, Lunar Roving Vehicle, Sojourner, Spirit & Opportunity, and Viking 1 & 2. Mission detail sections start hidden. `script.js` switches between the archive and the selected detail view. An `IntersectionObserver` reveals headings, cards, and detail sections in a staggered sequence as they enter the viewport; each item stays visible after its first reveal. The back button and Escape return to the archive without reversing the reveal motion. This keeps the project simple and avoids a framework or server-side routing dependency.

| File or directory | Responsibility |
| --- | --- |
| `index.html` | Page content, navigation controls, mission cards, mission detail sections, and the closing references footer. |
| `style.css` | Shared layout, colors, responsive rules, image crops, mission-specific atmosphere, and footer styling. |
| `script.js` | Landing-to-mission and mission-to-landing navigation. |
| `images/missions/` | Mission photography used by cards, heroes, and galleries. |
| `images/team/` | Compressed portraits used by the footer team cards. |
| `images/space/landing-cosmos.svg` | Hand-authored decorative starfield, nebula, sun, galaxy, and satellite illustration for the landing hero. |
| `PHOTO-CREDITS.md` | Image captions, archive IDs, source links, and local asset mapping. |
| `LICENSE` | MIT license for original project code and documentation. |
| `THIRD-PARTY-NOTICES.md` | Separate rights and reuse notes for media, fonts, and dependencies. |
| `CONTRIBUTING.md` | Contribution workflow and content/image requirements. |
| `wiki/` | GitHub Wiki-ready Markdown pages and navigation sidebar. |
| `docs/GITHUB-WIKI-PUBLISHING.md` | Instructions for copying the prepared pages into the GitHub Wiki repository. |
| `vercel.json` | Vite build and output settings for Vercel. |
| `docs/VERCEL-DEPLOYMENT.md` | Vercel setup and missing-source troubleshooting. |
| `.github/workflows/azure-static-web-apps.yml` | Manually triggered Azure Static Web Apps workflow. |

## 5. Edit mission copy or navigation

1. Find the mission’s section in `index.html` by its page ID, such as `id="kepler-page"`.
2. Edit the visible text and keep the surrounding headings and section structure intact.
3. To add a mission card, follow an existing `.prototype-card` in the landing page. Give it an image, mission title, and link/ID that match the navigation handler.
4. Add the card click and back-button behavior in `script.js`. The element IDs in the HTML and JavaScript must match exactly, including letter case.
5. Use semantic headings in order and give informative images useful `alt` text. Decorative backgrounds should remain hidden from assistive technology.

The mission content and asset groupings are project material. Check the supplied source and photo credits before changing factual copy or attributing an image.

## 6. Add or replace a photograph

1. Put the image under `images/missions/` (use `images/missions/supplied/` for the existing supplied-image group).
2. Prefer a reasonably sized JPEG or WebP for photographs. Keep the original source elsewhere if it is needed for future editing; the website only needs the optimized web copy.
3. Update the relevant `src` in `index.html`. Card images use `.prototype-card-image`; mission title images use `.mission-hero-image`; gallery images are in each mission gallery section.
4. Adjust the existing mission-specific `object-position` rule in `style.css` only when the crop needs to move. Keep the full image available in the gallery when a card or hero crop omits part of the frame.
5. Add the caption, image ID when known, source link, and local filename to the correct table in `PHOTO-CREDITS.md`.
6. Check the image at desktop and phone widths. Confirm that it loads from its local path and that its credit is present.

Do not assume a source image can be reused without conditions. Check its source record and any applicable terms before using it outside the project.

## 7. Update the team profiles

The compact team cards are in the `team-section` near the end of `index.html`. The first three portraits are under `images/team/`. Sara Maazouz’s card currently uses a designed initials placeholder; replace that placeholder element with an `<img>` pointing to her photo in `images/team/`, and keep the existing name and role text. The grid adapts from four columns to two and then one on narrower screens.

## 8. Adjust the space backgrounds

The landing hero uses `images/space/landing-cosmos.svg`, a scalable local vector asset. Edit its colors or decorative shapes directly in the SVG. The separate landing-page star layers and each mission page’s planet/ring palette are near the end of `style.css` under **SPACE ATMOSPHERES**. Each mission has three CSS color variables (`--mission-planet`, `--mission-ring`, and `--mission-glow`), grouped by its page ID. These are decorative layers behind page content; preserve readable text contrast and the existing hero photography.

## 9. Production build

```sh
npm run build
npm run preview
```

The build output is the contents of `dist/`. It can be served from any static host that supports HTML, CSS, JavaScript, and image files. Rebuild after the final edits before uploading the production copy. For this project, mission navigation is handled in the browser, so it does not need server-side route rules.

## 10. Publish the source on GitHub

Create an empty repository on GitHub, then run these commands in the project root. Replace the remote URL with the one GitHub shows for your repository:

```sh
git init
git add .
git commit -m "Prepare The Forgotten Explorers site"
git branch -M main
git remote add origin https://github.com/ACCOUNT/REPOSITORY.git
git push -u origin main
```

If the folder is already a Git repository, skip `git init`. If `origin` already exists, check it with `git remote -v` and update it with `git remote set-url origin <repository-url>` instead of adding a second remote. Do not add `node_modules/`, `dist/`, credentials, or private environment files. Review the staged file list before committing.

## 11. Deployment workflow already in the repository

`.github/workflows/azure-static-web-apps.yml` is available from the Actions tab and runs only when manually dispatched. Uploading or pushing the repository will not start a deployment. To use it later, set the repository secret `AZURE_STATIC_WEB_APPS_API_TOKEN` in GitHub’s repository settings, then choose the workflow and select **Run workflow**. This workflow is for Azure; pushing the source to GitHub does not publish the site to GitHub Pages. For another host, build with `npm run build` and publish `dist/` using that host’s static-site instructions.

For Vercel, use the project root that contains `index.html`, `script.js`, `style.css`, and `package.json`. `vercel.json` specifies the Vite framework, `npm run build`, and `dist` output. See [Vercel deployment notes](VERCEL-DEPLOYMENT.md) if the build reports missing source files.

## 12. Troubleshooting

- **`npm` is not found:** install Node.js, close and reopen the terminal, then check `node --version` and `npm --version`.
- **A local address does not open:** leave `npm run dev` running and use the exact address printed by Vite.
- **A page or image is missing:** check the path and capitalization in `index.html`; hosted systems may treat `Image.webp` and `image.webp` as different names.
- **The production preview is stale:** run `npm run build` again before `npm run preview`.
- **An Azure deployment fails:** confirm the token secret is set and review the failed workflow run in the repository’s Actions tab.

## 13. License and ownership

Original project code and documentation are released under the MIT License in `LICENSE`. Photographs, team portraits, and other third-party media are excluded from that license and remain subject to their own rights and terms. See `PHOTO-CREDITS.md` and `THIRD-PARTY-NOTICES.md` before reusing them. Attribution alone does not grant additional rights.
