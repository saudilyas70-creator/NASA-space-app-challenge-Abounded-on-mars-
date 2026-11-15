# Design and Accessibility

The site uses a dark, space-themed visual system with responsive mission cards, locally stored photography, and separate atmospheres for the landing page and mission views. Layout and motion styles are in `style.css`.

## Motion

The scroll reveal is one-way: sections and cards appear as they enter the viewport and remain visible after the visitor scrolls past them. Returning to the landing page with a back button or Escape does not play a reverse reveal. The page also respects the browser’s reduced-motion preference.

## Content and controls

- Keep heading levels in a logical order.
- Give informative images useful `alt` text.
- Keep decorative images hidden from assistive technology.
- Preserve keyboard access to links and buttons, including the mission back controls.
- Keep text readable over background photography and space effects.

When changing spacing or responsive styles, review the page at desktop and narrow phone widths.
