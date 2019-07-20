# CSS Grid

## What Is CSS Grid
- Grid layout system for CSS
- Similar to flexbox (more powerful but a bit more difficult)
- Two-dimensional layouts
- Can use "align-items", "justify-content", etc
- Partial support for IE11

### How It Works
- **display: grid;** /* Creates a "**grid**" */
- All direct child elements are "**grid items**"
- "**grid-template-columns**" defines width and number of cols

The difference between **flex** and **grid** is, _flex_ is not capable of two dimensional layout, it is only used for a single row or column. With _grid_ you can have two dimensional layout.

### Grid vs Flex
- It is NOT one or the other!
- Use CSS Grid for outter elements and grid-like layouts
- Use Flex for simple alignment (Inner elements, menu items, etc)

## Grid Basics & Columns
Flexbox knowledge will benefit you in using grid because they work in similar way where we take the element and set it as a container grid like we are doing with flex. Then it all makes all the child elements of that parent a grid items. And we can add specific properties to the parent to affect the grid items.

```css
.grid {
  display: grid;
  /* grid-template-columns: 200px 200px 200px; */
  /* grid-template-columns: repeat(3, auto); */
  grid-template-columns: 1fr 2fr 2fr;
  grid-gap: 1rem;
}
```

## Grid Rows
**Implicit grid/rows** are the ones we didn't manually set, but it was automatically set by itself.

```css
.grid {
  display: grid;
  grid-template-rows: 1fr 2fr 3fr;

  /* Set implicit rows */
  grid-auto-rows: 3fr;
}
```

## Spanning Columns & Rows
```css
.item:first-child {
  /* grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 3; */

  grid-column: 1 / span 3;
  grid-row: 1 / span 2;
}
```

## Auto-Fit & Minmax
Auto-fit & minmax that can make you grid kind of responsive, it's good for image gallery but not with regular website layout.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}
```

## Grid Template Areas
**grid-template-areas** property specifies _areas_ within the _grid_ layout. You can name _grid_ items by using the **grid-area** property, and then reference to the name in the **grid-template-areas** property.

Each _area_ is defined by apostrophes. Use a period sign to refer to a _grid_ item with no name.

```css
.container {
  display: grid;
  grid-template-areas: 
    'header header header'
    'content content sidebar'
    'box-1 box-2 box-2'
    'box-3 box-3 box-3'
    'footer footer footer';
  grid-gap: 1rem;
}

.header {
  grid-area: header;
}
```

## Media Queries & The Grid
```css
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

@media(max-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media(max-width: 540px) {
  .grid {
    grid-template-columns: repeat(1, 1fr);
  }
}
```