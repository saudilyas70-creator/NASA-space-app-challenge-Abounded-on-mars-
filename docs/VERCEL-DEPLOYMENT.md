# Deploy on Vercel

This is a Vite project. The root directory selected in Vercel must contain all four of these files:

```text
index.html
script.js
style.css
package.json
```

The repository includes `vercel.json` with the Vite framework preset, `npm install`, `npm run build`, and `dist` as the output directory.

## Vercel project settings

In the Vercel project’s **Settings → Build and Deployment**, use:

| Setting | Value |
| --- | --- |
| Framework Preset | Vite |
| Root Directory | The folder containing `index.html`, `script.js`, `style.css`, and `package.json` |
| Install Command | `npm install` |
| Build Command | `npm run build` |
| Output Directory | `dist` |

If the repository contains a parent folder around the app, set **Root Directory** to that app folder. Do not set it to `dist`; Vercel must run the build from the source project root.

## Resolve missing entry assets

An error such as `Failed to resolve /script.js` together with a warning that `style.css` cannot be found means the Vercel build checkout cannot see those files next to its `index.html`. Check the GitHub repository itself and confirm that `index.html`, `script.js`, `style.css`, `package.json`, `package-lock.json`, and the `images/` directory are committed inside the selected Root Directory. The HTML uses relative `./script.js` and `./style.css` references so the app can be built from its project root.

The Vercel settings file cannot compensate for missing source files or a Root Directory pointed at the wrong folder. Commit the complete project source, then redeploy.
