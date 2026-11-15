# Contributing

Thanks for helping improve The Forgotten Explorers. Keep changes focused and preserve the project’s supplied content and image attributions.

## Local setup

Use the project root (the folder containing `package.json`):

```sh
npm install
npm run dev
```

Before submitting a change, build the static site:

```sh
npm run build
```

## Content and images

- Use project-provided references when editing mission facts; do not add unsupported mission data.
- Keep card, hero, and gallery image choices relevant to their captions.
- For each new or replaced image, update `PHOTO-CREDITS.md` with the available caption, source, image ID, and local path.
- Verify reuse terms before adding an image. The MIT license does not cover images, team portraits, or other third-party media; see `THIRD-PARTY-NOTICES.md`.
- Preserve meaningful alternative text, keyboard access, reduced-motion support, and responsive layouts.

## Pull requests

Describe what changed and which page or behavior it affects. Include a screenshot for visible layout changes when practical. Note whether `npm run build` completed successfully.

## License

Original project code and documentation are provided under the MIT License in `LICENSE`. Third-party assets retain their separate rights and terms.
