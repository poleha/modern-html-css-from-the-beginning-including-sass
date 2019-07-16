# HTML Basics

## Section Intro
### Absolute Beginners
- The content in this section is for absolute beginners
- Feel free to skip this section if you are comfortable with HTML markup

### What Will We Cover
- What Is HTML?
- Tags & Attributes
- Page Structure
- Meta Tags
- VSCode Live Server Setup
- Keyboard Shortcuts
- Forms & Input
- Links & Images
- Tables & Lists
- Block vs Inline
- Div, Span, ID, Class
- HTML Entities
- HTML5 Semantic Tags

## Create & Open HTML Pages
On windows machine, go to View Tab in Explorer, then go to Options then click "Change folder and search options" make sure that the "Hide extension for know files" is uncheck.

### Tag Syntax
- Elements surrounded in angle brackets
- Usually have a start & end tag
- Some tags close themeselves (Remnant of XHTML)

```html
<!-- Start & End Tag -->
<h1>Hello</h1>
<p>Welcome to my websites</p>

<!-- Self Closing Tags -->
<br> <!-- Valid in HTML5 -->
<br /> <!-- Valid in HTML5 & XHTML -->
```

## Doctype & Basic Layout
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Website</title>
  </head>
  <body>
    <!-- This is a comment -->
    <h1>My Website</h1>
    <p>This is my very first website.</p>
  </body>
</html>
```

## Meta Tags & Search Engines
### Attributes
- describe the properties of the tag

```html
<meta charset="UTF-8"> <!-- specifies the character encoding of the page which is the default for unicode -->

<meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- very important for responsive web design, making the website responsive to different screen sizes -->

<meta http-equiv="X-UA-Compatible" content="id=edge"> <!-- ie referring to the old internet explorer browser which is not used very much at all anymore, windows switch to edge so were basically saying we want to use edge standards -->
```

### Search Engine related Tag
```html
<title>My Website</title>

<meta name="description" content="This is my website description">

<meta name="keywords" content="web development, web design"> <!-- 8-12 words -->
<meta name="robots" content="NOINDEX, NOFOLLOW"> <!-- Do not index page, If you don't want your site to rank in search engine -->
```

## Headings, Paragraphs & Typography
```html
<!-- Headings -->
<h1>Heading 1</h1> <!-- Good practice to only have one h1 per page-->
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>

<!-- Paragraph -->
<p>Lorem ipsum dolor sit <strong>exercitationem</strong>! Facilis <em>voluptates</em> autem itaqosam <del>impedit</del> explicabo mlla in.</p>

<!-- Line Break -->
<br>
<br>
Itaque ratione iusto, dolor culpa pariatur!

<!-- Horizontal Rule -->
<hr>
<p>facilis obcaecati dolor deleniti dolores?</p>
```

## Links, Images & Attributes
```html
<!-- External link on the same tab-->
<a href="https://google.com">Google link</a>

<!-- External link on a new tab-->
<a href="http://google.com" target="_blank">Google link on a new tab</a>

<!-- Internal link -->
<a href="/reference.html">Reference</a>

<!-- Local image -->
<img src="./img/sample.jpg" alt="My Image" width="200">

<!-- Remote image -->
<img src="https://source.unsplash.com/200x200/?building" alt="My Image 2">
```

## Lists & Tables
```html
<!-- Unordered lists -->
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<!-- Ordered Lists -->
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>

<!-- Nested lists -->
<ul>
  <li>Item 1</li>
  <li>Item 2
    <ul>
      <li>Nested Item 1</li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>

<!-- Tables -->
<table style="width: 600px">
  <thead>
    <tr>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>Doe</td>
      <td>jdoe@gmail.com</td>
    </tr>
    <tr>
      <td>Kate</td>
      <td>Smith</td>
      <td>kate@gmail.com</td>
    </tr>
  </tbody>
</table>
```

## Forms & Input
```html
<form action="process.php">
  <!-- Text -->
  <label for="name">Name</label><br>
  <input type="text" id="name" name="name" value="John Doe">

  <!-- Email -->
  <label for="email">Email</label><br>
  <input type="email" name="email" id="email" placeholder="Enter an email">

  <!-- Number -->
  <label for="age">Age</label><br>
  <input type="number" name="age" id="age">

  <!-- Date -->
  <label for="bithdate">Birthdate</label><br>
  <input type="date" name="birthdate" id="birthdate">

  <!-- Textarea -->
  <label for="message">Message</label>
  <textarea name="message" id="message" cols="50" rows="5"></textarea>

  <!-- Select -->
  <label for="gender">Gender</label>
  <select name="gender" id="gender">
    <option value="male" selected>Male</option>
    <option value="female">Female</option>
    <option value="other">Other</option>
  </select>

  <!-- Radio -->
  <label for="membership">Membership</label>
  <input type="radio" name="membership" value="simple" id="simple"> Simple
  <input type="radio" name="membership" value="standard" id="standard" checked> Standard
  <input type="radio" name="membership" value="super" id="super"> Super

  <!-- Checkbox -->
  <label for="membership">I Like..</label>
  <input type="checkbox" name="likes" value="bike" id="bike"> Bike
  <input type="checkbox" name="likes" value="car" id="car"> Car
  <input type="checkbox" name="likes" value="boat" id="boat"> Boat

  <!-- Input submit -->
  <input type="submit" value="Submit">

  <!-- Button submit -->
  <button type="submit">Submit</button>
  <button type="reset">Reset</button>
</form>
```

## Block & Inline Level Elements
**Block level** it goes across the whole page and pushes the next one into the next line.

**Inline Level** it goes next to it, and it does not push it into the next line because it does not span all the way across.

## Divs & Spans, Classes & Ids
**Classes** and **Ids** does not have functional difference, they don't behave differently, can style them the exact way.
- **Classes** can repeat, can have the same class in the same page, can have multiple classes separated by space
- **Ids** good practice not to repeat id's in the same page.

**Divs** and **span** are only use for styling purposes, they have no semantic meaning.
- **Div** is a block level element pushes the next thing down
- **Span** is a inline level element, stay in its place

## HTML Entities
```html
<!-- Non breaking space -->
<p>Hello, my name is &nbsp; &nbsp; &nbsp; &nbsp;Joe</p>

<!-- Greater than and less than -->
<p>5 &gt; 2</p>
<p>5 &#62; 2</p>
<p>1 &lt; 2</p>
<p>1 &#60; 2</p>

<!-- Copyright -->
<p>&copy;</p>
<p>&reg;</p>

<!-- Currency -->
<p>&cent;</p>
<p>&pound;</p>
<p>&yen;</p>
<p>&euro;</p>

<!-- Suits -->
<p>&spades;</p>
<p>&clubs;</p>
<p>&hearts;</p>
<p>&diams;</p>

<!-- Computer code -->
<code>
  &lt;?php echo 'Hello' ?&gt;
</code>
<p>Save the file by pressing <kbd>Ctrl + S</kbd></p>
```

## HTML5 Semantic Tags
```html
<header> <!-- Usually goes at the top -->
<footer> <!-- Usually goes at the bottom -->
<nav> <!-- Navigation sometimes inside the header or underneath -->
<main> <!-- Some wrap around the whole content -->
<section> <!-- about, features -->
<article> <!-- article, blog post -->
<aside> <!-- sidebar content, it's not the focus of the page, can be ads or category section of the -->
```