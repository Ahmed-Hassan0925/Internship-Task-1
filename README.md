[README.md](https://github.com/user-attachments/files/32678501/README.md)
# Aperture — Image Gallery

A responsive image gallery with category filtering and a full-screen lightbox, built with plain HTML, CSS, and JavaScript — no frameworks or dependencies.

## Features

- **Responsive grid layout** — automatically reflows from multiple columns on desktop to a single column on small screens using CSS Grid (`auto-fill`).
- **Lightbox view** — click any image to open it full-screen with a smooth fade transition.
- **Navigation** — step through images using the on-screen prev/next arrows or the left/right arrow keys. Press `Esc` or click outside the image to close.
- **Category filters** — filter the gallery by `landscape`, `urban`, or `people`, or view `all`.
- **Hover effects** — images scale slightly and captions fade in on hover.
- **Lazy loading** — images use `loading="lazy"` so off-screen photos aren't fetched until needed.

## File structure

```
task1-image-gallery.html   → single self-contained file (HTML + CSS + JS)
```

Everything — markup, styling, and behavior — lives in this one file, so you can open it directly in a browser with no build step or server required.

## How to run it

Just open `task1-image-gallery.html` in any modern browser (Chrome, Firefox, Safari, Edge). No installation needed.

## How to customize

**Change the photos** — edit the `photos` array near the top of the `<script>` block:

```js
const photos = [
  { src: "your-image-url-or-path.jpg", title: "Your caption", category: "landscape" },
  // ...
];
```

- `src` can be a URL or a relative path to a local image file.
- `category` can be any string — the filter buttons are generated automatically from whatever categories appear in the array, so adding a new category (e.g. `"animals"`) automatically adds a new filter button.

**Change the color palette** — edit the CSS custom properties at the top of the `<style>` block:

```css
:root{
  --bg: #14130f;        /* page background */
  --ink: #f2ede2;       /* main text color */
  --accent: #d99a3f;    /* active filter / hover accent color */
}
```

**Change the grid density** — adjust the `minmax()` value in `.grid`:

```css
.grid{
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
}
```
A smaller minimum (e.g. `180px`) fits more columns on the same screen width.

## Browser support

Uses standard, widely supported CSS and JavaScript (CSS Grid, `aspect-ratio`, template literals, `IntersectionObserver`-free lazy loading via the native `loading` attribute). Works in all current versions of Chrome, Firefox, Safari, and Edge.

## Credits

Sample images are placeholder photos served from [Picsum Photos](https://picsum.photos), seeded so the same images load consistently. Replace the `src` values with your own images before deploying.
