# Troubleshooting

| Problem | What to check |
| --- | --- |
| `npm` is not found | Install Node.js, reopen the terminal, then check `node --version` and `npm --version`. |
| The local address does not open | Leave `npm run dev` running and use the exact address Vite printed. |
| A page or image is missing | Check the path and letter case in `index.html`; some hosts treat upper- and lowercase filenames differently. |
| The production preview is stale | Run `npm run build` again before `npm run preview`. |
| An Azure workflow run fails | Check that the repository secret `AZURE_STATIC_WEB_APPS_API_TOKEN` is present, then review the failed Actions run. |
| A mission card does not open | Check that its ID and page ID match an entry in `missionRoutes` in `script.js`. |
| Motion is not visible | Scroll down through the page; a browser reduced-motion setting turns the reveal animation off. |

For more detail, see `docs/TECHNICAL-DOCUMENTATION.md` in the source repository.
