# Publish the GitHub Wiki

The pages in the project’s `wiki/` folder are ready-to-copy GitHub Wiki sources. GitHub stores a repository Wiki separately from the source repository. This project folder does not currently identify a GitHub remote, so the pages are prepared locally and are not published online.

## Publish

1. Open the repository on GitHub and enable its Wiki if it is available.
2. Replace `OWNER` and `REPOSITORY` below with the repository owner and name shown on GitHub.
3. Clone the Wiki repository, copy the Markdown pages into its root, and push them.

```sh
git clone https://github.com/OWNER/REPOSITORY.wiki.git
cp /path/to/THE-FORGOTTEN-EXPLORERS/wiki/*.md REPOSITORY.wiki/
cd REPOSITORY.wiki
git add .
git commit -m "Add project wiki"
git push
```

The included `Home.md` becomes the Wiki landing page, and `_Sidebar.md` supplies the navigation menu. `Photo-Credits.md` mirrors the project’s `PHOTO-CREDITS.md` source so the Wiki can show the full attribution list. If credits are updated in the source repository later, copy the revised file into `wiki/Photo-Credits.md` before syncing the Wiki.
