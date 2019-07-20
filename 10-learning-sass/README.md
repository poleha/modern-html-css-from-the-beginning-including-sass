# Learning Sass

## What Is Sass?
- **S**yntactically **A**wesome **S**tyle**S**heet
- CSS Preprocessor / Precompiler
- Enhances the functionality of CSS
- Other preprocessors include Less and Stylus

### How Does Sass Work?
- Sass uses .scss or .sass file extensions
- The browser does NOT read Sass, it must be compiled
- Sass files are compiled to normal CSS files
- There are many different types of Sass compilers (cli & gui)

### What Does Sass Offer?
- Variables
- Nesting
- Partials / Imports
- Functions & Mixins
- Conditionals
- Inheritance
- Operators & Calculations
- Color Functions

### .scss vs .sass
**.scss** is usually preferred over **.sass** as it uses the same syntax as regular css

SASS
```sass
$color: red
$color2: lime

a
  color: $color
  &:hover
    color: $color2
```

SCSS
```scss
$color: #f00;
$color2: #0f0;

a {
  color: $color;
  &:hover {
    color: $color2;
  }
}
```

CSS
```css
a {
  color: red;
}
  a:hover {
    color: lime;
  }
```

## Environment Setup With Node-Sass
Download and Install the LTS or Current version of Node.js.

Check the npm version:
```sh
npm --version
```

Create a package.json file since we are installing anything with npm.
```sh
npm init
# to answer it all by default
npm init -y

# to install node-sass
npm install node-sass 
```

Modify package.json file scripts:
```json
"scripts": {
  "sass": "node-sass -w scss/ -o dist/css/ --recursive"
}
```

Then run sass to contantly watch the scss folder and sass file it it. As soon as we made our changes and save it will compile it into dist css.
```sh
npm run sass 
```

## Koala Sass Compiler - GUI Alternative
Koala is an open source GUI compiler for pre-processing languages.

### Features
- Multi-language Support
- Real-time Compilation
- Compile Options Support
- Compression
- Error Notification
- Cross-platform

### Installation Guide
Download your system version of the installation package from the [koala](http://koala-app.com/) official website.

### Add project
Drag and drop a folder or click on the plus icon in the top left corner and select your project folder.

### Change output path
By default, the output path is the file directory. If you want to change it, right-click on the file and select "Set output path". You can also click the edit icon near the output path.

## Variables & Partials
Think of **variables** as a way to store information that you want to reuse throughout your stylesheet. Sass uses the `$` symbol to make something a variable.

```scss
$font-stack: Arial, Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

You can create **partial** Sass files that contain little snippets of CSS that you can include in other Sass files. This is a great way to modularize your CSS and help keep things easier to maintain. A partial is simply a Sass file named with a leading underscore. You might name it something like \_partial.scss. The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file. Sass partials are used with the @import directive.

## Nesting & Structuring
Sass will let you nest your CSS selectors in a way that follows the same visual hierarchy of your HTML. Be aware that overly nested rules will result in over-qualified CSS that could prove hard to maintain and is generally considered bad practice.

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

## Inheritance & Contrast
This is one of the most useful features of Sass. Using @extend lets you share a set of CSS properties from one selector to another. It helps keep your Sass very DRY. In our example we're going to create a simple series of messaging for errors, warnings and successes using another feature which goes hand in hand with extend, placeholder classes. A placeholder class is a special type of class that only prints when it is extended, and can help keep your compiled CSS neat and clean.

```scss
/* This CSS will print because %message-shared is extended. */
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

// This CSS won't print because %equal-heights is never extended.
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
}
```

What the above code does is tells `.message`, `.success`, `.error`, and .`warning` to behave just like `%message-shared`. That means anywhere that `%message-shared` shows up, `.message`, `.success`, `.error`, & .`warning` will too. The magic happens in the generated CSS, where each of these classes will get the same CSS properties as `%message-shared`. This helps you avoid having to write multiple class names on HTML elements.

You can extend most simple CSS selectors in addition to placeholder classes in Sass, but using placeholders is the easiest way to make sure you aren't extending a class that's nested elsewhere in your styles, which can result in unintended selectors in your CSS.

Note that the CSS in `%equal-heights` isn't generated, because `%equal-heights` is never extended.

## Functions, Mixins & More
**Functions** allow you to define complex operations on SassScript values that you can re-use throughout your stylesheet. They make it easy to abstract out common formulas and behaviors in a readable way.

Functions are defined using the @function at-rule, which is written `@function <name>(<arguments...>) { ... }`. A function’s name can be any Sass identifier. It can only contain universal statements, as well as the @return at-rule which indicates the value to use as the result of the function call. Functions are called using the normal CSS function syntax.

```scss
@function pow($base, $exponent) {
  $result: 1;
  @for $_ from 1 through $exponent {
    $result: $result * $base;
  }
  @return $result;
}

.sidebar {
  float: left;
  margin-left: pow(4, 3) * 1px;
}
```

**Mixin** lets you make groups of CSS declarations that you want to reuse throughout your site. You can even pass in values to make your mixin more flexible. A good use of a mixin is for vendor prefixes. Here's an example for transform.

```scss
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}
.box { @include transform(rotate(30deg)); }
```

To create a mixin you use the `@mixin` directive and give it a name. We've named our mixin `transform`. We're also using the variable `$property` inside the parentheses so we can pass in a transform of whatever we want. After you create your mixin, you can then use it as a CSS declaration starting with `@include` followed by the name of the mixin.