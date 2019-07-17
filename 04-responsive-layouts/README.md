# Intro To Responsive Layouts

## Responsive Design
Using **HTML/CSS** to make a website or app layout adapt to different screen sizes
- It is a necessity to build responsive layouts
- Layouts should render on any form factor

### Practice To Use
- Set the viewport/scale
- Use fluid widths as oppose to fixed
- Media queries - Different css styling for different screen sizes
- Rem units over px
- Mobile first method

## Media Queries
```css
/* Smartphones */
@media(max-width: 500px) { }

/* Smartphones */
@media(min-width: 501px) and (max-width: 768px) { }

/* Normal */
@media(min-width: 769px) and (max-width: 1200px) { }

/* Widescreen */
@media(min-width: 1201px) { }

/* Landscape */
@media(max-height: 500px) { }
```

```html
<!-- External media query stylesheet to apply only in a specific screen width -->
<link rel="stylesheet" media="screen and (max-width: 768px)" href="mobile.css">
```

## Em & Rem Units
html or the root **font-size** is always gonna be **16px** by default.

- Em units are based on their _parent_ element.
- Rem is based on the _root_ element.

Common thing that others do is setting their root element **font-size** to **10px** when using rem units, bacause it's easier to figure out what the sizes are gonna be.

To make it even more responsive set the **font-size** to a _percentage_, **62.5%** which is gonna be **10px**.

Another reason to use rem units is for _accesibility_ and _browser_ settings.

## Vh & Vw Units
Each of viewport height is a slice across and its always gonna be 100 of them. No matter how big or small the browser is, its always 100vh and each one is a slice.

Screen is always **100%** viewport size.

Viewport sizes is great for landing page and is used more often for that.