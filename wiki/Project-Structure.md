# Project Structure

| Path | Purpose |
| --- | --- |
| `index.html` | Landing page, mission detail views, and closing references section. |
| `style.css` | Layout, responsive rules, visual styling, image crops, and space backgrounds. |
| `script.js` | Mission view switching and one-way scroll reveal behavior. |
| `images/missions/` | Mission card, hero, and gallery images. |
| `images/team/` | Project team portraits and the reserved Sara Maazouz photo slot. |
| `images/space/` | Decorative space illustration assets. |
| `PHOTO-CREDITS.md` | Captions, image IDs, local filenames, and source links. |
| `LICENSE` | MIT license for original project code and documentation. |
| `THIRD-PARTY-NOTICES.md` | Separate rights and reuse notes for media, fonts, and dependencies. |
| `CONTRIBUTING.md` | Local setup and contribution guidance. |
| `docs/TECHNICAL-DOCUMENTATION.md` | Full project setup, editing, and publishing guide. |
| `wiki/` | Markdown source pages prepared for the repository’s GitHub Wiki. |
| `package.json` | Vite scripts and development dependency. |
| `package-lock.json` | Locked npm dependency versions. |
| `vercel.json` | Vercel build and output settings. |
| `.github/workflows/` | Manual Azure Static Web Apps workflow. |
| `dist/` | Generated production output; recreated by `npm run build`. |

`node_modules/` and `dist/` are generated directories and are excluded by `.gitignore`.
