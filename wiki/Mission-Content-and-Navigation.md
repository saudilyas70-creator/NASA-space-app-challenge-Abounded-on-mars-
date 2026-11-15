# Mission Content and Navigation

## Mission views

The landing page links to these detail views:

- Apollo 11 Lunar Module
- Kepler / K2
- Surveyor 3
- Lunar Roving Vehicle
- Sojourner
- Spirit & Opportunity
- Viking 1 & 2

The content and view markup are in `index.html`. Each mission view has a page ID and a back button. `script.js` connects those controls to the selected view.

## Edit existing content

1. Find a view in `index.html` by its ID, such as `kepler-page`.
2. Update the copy while preserving the existing section and heading structure.
3. If factual mission content changes, use the supplied project material and check its source before editing.
4. Keep image captions and credits in sync with `PHOTO-CREDITS.md`.

## Add a mission view

1. Add the detail markup and a landing-page card in `index.html`.
2. Give the page, card, and back button unique IDs.
3. Add the matching elements to the `missionRoutes` list in `script.js`.
4. Add any mission-specific styling to `style.css`.
5. Verify the card opens its view and both the back button and Escape key return to the landing page.

The scroll reveal uses `IntersectionObserver`. Items reveal in a staggered sequence as they enter the viewport and stay visible when the visitor scrolls back up. Browsers that request reduced motion receive the content without reveal animation.
