# CSS Basics

## Section Intro
### The Goal
- We will look at **fundamental CSS** properties
- The goal is to get you ti really <u>understand</u> what is going on rather than just creating a website and have you follow along

### What We Will Cover
- Implementing CSS
- Using Selectors
- Fonts, Colors, etc
- Backgrounds & Borders
- Box Model / Margin & Padding
- Floating & Alignment
- Display Property
- Link & Button Styling
- Creating Menus
- Positioning
- Form Styling
- Dev Tools

## Implementing CSS
HTML is very important but by itself its very ugly, we need CSS to style it, move things around, align, add colors, background and anything else that has to do with layout and style.

### CSS Syntax
```css
h1 { color: red; }
```

- **h1** is a _selector_
- **{** is a declaration start
- **color** is a _property_
- **:** is a property/value _separator_
- **red** is a _value_
- **;** is a declaration separator
- **}** is a declaration end

### Inline CSS
```html
<h1 style="color: red;">Heading One</h1>
```

### Internal CSS
```html
<style>
  h1 { color: green; }
</style>
```

### External CSS
External CSS is the preferred way of doing it.

```html
<link rel="stylesheet" href="css/style.css">
```

**Note**: Separation of concerns, keep your styling out of your marking.

## Basic CSS Selectors
### Element Selectors
```css
h2 { color: green; }
```

### . is for Classes
```css
.primary-heading { color: blue; }
```

### # is for IDs
```css
#welcome { color: red; }
```

### Multiple Selectors
Separated by commas (,)
```css
#welcome,
.primary-heading,
h2 {
  color: coral;
}
```

### Nested Selectors
```css
/* Targetting the paragraph inside the id welcome. */
#welcome p {
  font-size: 20px;
}
```

## Fonts In CSS
_Web Safe Fonts_ are mostly available in all browsers.

Google Fonts
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto">
```

```css
body {
  font-family: 'Roboto', sans-serif;
  font-size: 18px;
  line-height: 1.6em;
  /* font-weight: bold; */
  /* font-style: italic; */
}
```

### CSS Units: Absolute
- **cm** | Centimeters
- **mm** | Millimeters
- **in** | Inches
- **px** | Pixels (1px = 1/96th of 1in)
- **pt** | Points (1pt = 1/72 of 1in)
- **pc** | Picas picas (1pc = 12 pt)

### CSS Units: Relative
- **%**  | To parent element
- **em** | To font-size of parent element
- **rem**| To font-size of root element
- **vw** | To 1% of viewport width
- **vh** | To 1% of viewport height

## Color Types
### Color Name
```css
/* Color Name */
h1 { color: red; }

/* RGB (0-255) */
h1 { color: rgb(255, 0, 0); }

/* HEX (0-9/A-F) */
h1 { color: #ff0000; }
```

## Backgrounds & Borders
```css
.box-1 {
  background-color: blue;
  /* border-width: 3px;
  border-style: solid; 
  border-color: red; */ /* dotted, dashed*/
  border: 3px solid red; /* preferred way*/
  /* border-top: 3px solid blue; */
  border-radius: 10px;
  /* border-top-right-radius: 10px; */
}

.box-3 {
  /* background-image: url('./img/stars.jpg');
  background-repeat: no-repeat;
  background-position: 100px 100px;
  background-position: center top;
  background-size: cover; */
  background: url('./img/stars.jpg') no-repeat center center/cover;
  /* background-attachment: fixed; */
}
```

## Box Model, Margin & Padding
### Four Layers of Box Model
1. **Element**
2. **Padding** space inside the element
3. **Border**
4. **Margin** space outside the element

**CSS Reset** removes all the default styling.

```css
/* CSS Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.box {
  background-color: #f4f4f4;
  border: 2px solid #777;
  width: 500px;

  /* Padding on all sides */
  padding: 20px;

  /* Padding on per side */
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 10px;
  padding-left: 20px;

  /* Padding shorthand = top right bottom left */
  padding: 10px 20px 10px 20px;

  /* Padding shorthand = top/bottom left/right */
  padding: 10px 20px;


  /* Margin on all sides */
  margin: 20px;

  /* Margin on per side */
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;

  /* Margin shorthand = top right bottom left */
  margin: 10px 20px 10px 20px;

  /* Margin shorthand = top/bottom left/right */
  margin: 10px 20px;
}
```

## Float & Alignment
To center your content/layout, you need a _container_ element with a **class/id**, have a **width** to it and set the **margin** to _auto_.

```css
/* Adding box-sizing property for padding issues of float */
* {
  box-sizing: border-box;
}

.container {
  /* Using max-width for responsive design */
  max-width: 960px;
  margin: 30px auto;
}

/* Clear after using float */
.clr {
  clear: both;
}

.box p {
  /* Text Align */
  text-align: left;
  text-align: right;
  text-align: center;
  text-align: justify;
}

/* Add a width when doing a float */
#box-2 {
  width: 68%;
  float: left;
}
#box-3 {
  width: 30%;
  float: right;
}
```

## Link State & Button Styling
```css
a {
  color: #333;
  text-decoration: none; /* to remove underline for links */
}

/* HOVER state, change style when hover */
a:hover {
  color: coral;
  /* font-size: 17px; */
  /* text-decoration: underline; */
}

/* VISITED state, style when link was visited */
a:visited {
  color: red;
}

/* ACTIVE state, style when we click */
a:active {
  color: red;
}

/* Button Styling */
.btn {
  background-color: #4c6ca0;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

.btn:hover {
  background-color: #446190;
  color: #f4f4f4;
}
```

## Navigation Menu Styling
```html
<ul class="navbar">
  <li>Home</li>
  <li>About</li>
  <li>Services</li>
  <li>Contact</li>
</ul>

<ul class="side-menu">
  <li>Home</li>
  <li>About</li>
  <li>Services</li>
  <li>Contact</li>
</ul>
```

```css
/* Navbar Styling */
.navbar {
  list-style: none;
  margin: 0;
  padding: 0;
  background-color: #4c6ca0;
  border-radius: 5px;
  overflow: auto; /* to fix the background issue when using float */
}

.navbar li {
  float: left;
}

.navbar li a {
  display: block; /* to add padding */
  color: #fff;
  text-decoration: none;
  padding: 15px 20px;
}

.navbar li a:hover {
  background-color: #446190;
  color: #f4f4f4;
}
```

```css
/* Side Menu Styling */
.side-menu {
  width: 300px;
  list-style: none; /* remove the bullets */
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 20px;
}
.side-menu li  {
  line-height: 2.4em;
  border-bottom: 1px dotted #ddd;
}
.side-menu li:last-child {
  border: none;
}

.side-menu li a {
  color: #333;
  text-decoration: none;
}

.side-menu li a:hover {
  color: coral;
}
```

## Inline, Block & Inline-Block Display
```css
/* By default list items are block level, but can be change to be inline to create a horizontal menu navigation. */
li {
  display: inline;
}

/* Cannot set the margin to auto on an inline element, it needs to be block level. */
img {
  display: block;
  margin: auto;
}

/* Be default divs are display as block, inline-block is suitable */
.box {
  display: inline-block;
  width: 32.8%;
  padding: 20px;
  margin-bottom: 15px;
}
```

## Positioning
Everything by default has a position of static.

### Position Values
- **Static** | Not affected by tblr (top, bottom, left, right) properties/values
- **Relative** | tblr values cause element to be moved from its normal position
- **Absolute** | Positioned relative to its parent element that is positioned "relative"
- **Fixed** | Positioned relative to the viewport
- **Sticky** | Positioned based on scroll position

The heigher the **z-index**, then the closer to you.

```css
.box {
  width: 100px;
  height: 100px;
}
.container {
  position: relative;
  width: 500px;
  height: 500px;
  background-color: #333;
}
#box-1 {
  position: relative;
  top: 50px;
  left: 50px;
  z-index: 1;
  background-color: red;
}
#box-2 {
  position: absolute;
  top: 100px;
  left: 100px;
  background-color: yellow;
}
#box-3 {
  position: absolute;
  top: 100px;
  left: 100px;
  background-color: green;
}
#box-4 {
  position: fixed;
  background-color: blue;
}
#box-5 {
  position: sticky;
  top: 0;
  z-index: -1;
  background-color: orange;
}
```

## Aside: Visibility, Order & Negative Margin
```css
h1 {
  /* Completely remove the content from the DOM */
  display: none;

   /* Hide the content but still takes up the space */
  visibility: hidden;

  /* Important flag to take precedence over the other styles */
  color: red !important;
  color: blue;

  /* Negative margin is possible but its good to avoid it as much as possible */
  margin-top: -30px;
}
```