# 3D Hover Flip Menu

A lightweight, pure CSS navigation component that flips menu items in 3D on hover, revealing a secondary label and icon behind each button.

## Preview

Each menu item is a card with two faces:

- **Front** — dark background with a primary label and icon
- **Back** — red background with an alternate label and icon

Hovering a card rotates it 90° along the X-axis, flipping from front to back with a smooth 0.5s transition.

## Files

| File | Description |
|---|---|
| `3DHoverFlipMenu.html` | Markup and Font Awesome icon links |
| `3DHoverFlipMenu.css` | All styling and 3D flip animation |

## How It Works

The effect relies on three CSS features:

1. **`perspective`** on the parent `.flip-menu` container creates the 3D depth illusion.
2. **`transform-style: preserve-3d`** on each `<a>` tag allows its child elements to live in the same 3D space.
3. **`backface-visibility: hidden`** hides each face when it is rotated away from the viewer, so only one face is visible at a time.

On hover, the anchor element rotates `rotateX(90deg)`. The back face is pre-rotated `rotateX(-90deg)`, so it lands face-forward after the flip.

## Usage

1. Include both files in the same directory.
2. Open `3DHoverFlipMenu.html` in any modern browser — no build step required.
3. The Font Awesome icons load from a CDN, so an internet connection is needed for them to appear.

## Customisation

| What to change | Where |
|---|---|
| Menu labels and icons | `<span class="front">` / `<span class="back">` in the HTML |
| Front card colour | `.flip-menu a .front` → `background` |
| Back card colour | `.flip-menu a .back` → `background` |
| Page background colour | `body` → `background` |
| Flip speed | `.flip-menu a` → `transition: transform Xs ease` |
| Card size | `.flip-menu a` → `width` / `height` |
| Gap between cards | `.flip-menu` → `gap` |

## Browser Support

Works in all modern browsers that support CSS 3D transforms (Chrome, Firefox, Safari, Edge). Does not require JavaScript.

## Dependencies

- [Font Awesome 7](https://fontawesome.com/) — loaded via CDN for icons only. The flip animation works without it.
