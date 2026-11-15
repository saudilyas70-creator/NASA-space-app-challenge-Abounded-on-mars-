# Build and Publish

## Create and preview a production build

From the project root:

```sh
npm run build
npm run preview
```

Vite writes the static production site to `dist/`. Publish the contents of `dist/` with a static hosting provider when the site is ready to go live.

## GitHub source repository

The complete source, image assets, and documentation belong in the project repository. Keep `package.json`, `package-lock.json`, `index.html`, `style.css`, `script.js`, `images/`, and the project documentation. Do not commit `node_modules/`, `dist/`, credentials, or private environment files.

## Existing Azure workflow

The repository includes `.github/workflows/azure-static-web-apps.yml`. The project documentation describes it as manually triggered and requiring the `AZURE_STATIC_WEB_APPS_API_TOKEN` repository secret. A push to GitHub does not by itself publish the site through this workflow. GitHub Wiki pages are separate from the website build and do not deploy the site.

## Vercel

The project includes `vercel.json` with the Vite preset, `npm run build`, and `dist` output. In Vercel, set the Root Directory to the folder containing `index.html`, `script.js`, `style.css`, and `package.json`. A missing `script.js` or `style.css` build error usually means the selected root or the committed source files are incomplete; see `docs/VERCEL-DEPLOYMENT.md` in the source repository.

Original project code and documentation are licensed under MIT; the license is in the source repository’s `LICENSE` file. Photographs, team portraits, fonts, and other third-party material are excluded and retain their separate rights and terms. Review `THIRD-PARTY-NOTICES.md` and `PHOTO-CREDITS.md` before reusing them.
