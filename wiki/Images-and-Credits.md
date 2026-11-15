# Images and Credits

Mission images are stored locally so the site does not need remote image URLs at runtime. The image references and descriptions are maintained in the repository’s `PHOTO-CREDITS.md` file; the matching page is [[Photo Credits]].

## Replace or add an image

1. Add the optimized image under `images/missions/` (the existing supplied-image group is `images/missions/supplied/`).
2. Update the matching image path in `index.html`.
3. Keep the card image, title background, and gallery image selection appropriate to their placement.
4. Adjust the related `object-position` rule in `style.css` only when the crop needs to move.
5. Add or update the caption, archive ID when known, source link, and local filename in `PHOTO-CREDITS.md`.
6. Check the image at desktop and phone widths.

Use informative alternative text for content images. Keep decorative images hidden from assistive technology. Check the source record and reuse terms before publishing an image outside this project; a credit line alone does not grant reuse rights.

The project’s MIT license does not cover photographs, team portraits, or other third-party media. See [[License-and-Third-Party-Content]] and `THIRD-PARTY-NOTICES.md` in the source repository.

## Team portraits

The first three team portrait files are under `images/team/`. The Sara Maazouz profile is intentionally reserved as a placeholder. Replace it only when the project team provides her photo, and preserve the current name and role unless the project team directs otherwise.
