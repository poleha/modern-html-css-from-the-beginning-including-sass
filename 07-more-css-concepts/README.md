# More CSS Concepts - Advanced Selectors, Animation & More

## Targeted Selectors
```css
/* Direct Child */
div > p { background-color: #ddd; }

/* Directly After */
div + p {
  background-color: #333;
  color: #fff;
}

/* By Attribute */
a[target] {
  background-color: #ff0000;
  color: #fff;
}

/* Specific Attribute Values */
input[type="text"],
input[type="email"] {
  width: 100%;
  margin-bottom: 5px;
}
```

## nth-child Pseudo Selectors
```css
/* first-child */
li:first-child { color: red; }

/* last-child */
li:last-child { color: red; }

/* Position 3 */
li:nth-child(3) { color: purple; }

/* Every 3 */
li:nth-child(3n+0) { color: orange; }

/* Every 3 after 7 */
li:nth-child(3n+7) { color: yellow; }

/* Every odd */
li:nth-child(odd) { color: #ccc; }

/* Every even */
li:nth-child(even) { color: #ddd; }
```

## before & after Pseudo Selectors
Adding something before or after the element.
```css
.is-required:after { }

header:before { }
```

## Box Shadows
```css
.box {
  /* offset-x | offset-y | color */
  box-shadow: 10px 10px teal;

  /* offset-x | offset-y | blur-radius | color */
  box-shadow: 5px 5px 20px teal;

  /* Negative values */
  box-shadow: -5px -5px 20px teal;

  /* offset-x | offset-y | blur-radius | spread-radius | color */
  box-shadow: 3px 3px 10px 1px rgba(0, 0, 0, 0.3);

  /* inset | offset-x | offset-y | color */
  box-shadow: inset -3px -3px teal;

  /* Multiple Shadows */
  box-shadow: 3px 3px 10px teal, -3px -3px 10px olive;
}
```

## Text Shadows
```css
/* h-shadow | v-shadow | color */
h1.a { text-shadow: 0.2rem 0.2rem steelblue; }

/* h-shadow | v-shadow | blur */
h1.b { text-shadow: 0.4rem 0.3rem 0.7rem steelblue; }

/* White Text */
h1.c {
  color: #fff;
  text-shadow: 0.2rem 0.2rem 1rem steelblue;
}

/* Negetive Values */
h1.d { text-shadow: -0.4rem -0.3rem 0.7rem steelblue; }
```

## CSS Variables (Custom Properties)
**CSS variables** also called _custom properties_, they are just placeholders for values.

```css
/* CSS Variable Declaration */
:root {
  --container-max: 960px;
}

/* Implementation */
.container {
  max-width: var(--container-max);
}
```

## Keyframe Animation
When you animate, you're just taking a property that can be animated such as width, position, color, opacity something where you have a midpoint.

```css
@keyframes animate1 {
  /*
  from {
    top: 0;
  }

  to {
    top: 300px;
  }
  */

  0% {
    left: 0px;
    top: 0px;
  }

  25% {
    top: 0px;
    left: 300px;
  }

  50% {
    top: 300px;
    left: 300px;
  }

  75% {
    top: 300px;
    left: 0px;
  }

  100% {
    top: 0px;
    left: 0px;
  }
}
```

## CSS Transitions
**Transitional** properties that have an identifiable halfway point

- background-color 
- background-position 
- border-color 
- border-width 
- border-spacing 
- bottom 
- color
- font-size 
- font-weight 
- height left 
- letter-spacing 
- line-height 
- margin 
- max-height 
- max-width 
- min-height 
- min-width 
- opacity 
- outline-color 
- outline-offset 
- outline-width 
- padding right 
- text-indent 
- text-shadow 
- top 
- vertical-align 
- visibility 
- width 
- word-spacing 
- z-index */

## Transform Property
**Transform** property lets you rotate, scale, skew, or translate an element.

```css
.box:hover {
  transform: rotate(180deg);
  transform: skew(25deg);
  transform: scale(2);

  transform: translate(100px, 100px);
  transform: translate3d(100px, 100px, 100px);
}
```