# HTML

Created by Vince Chang </br>

Here is where I post useful information on HTML which is used for structuring
web content

#### HOW TO OPTIMIZE HTML

- [Compressing JPEG](https://compressjpeg.com/)
- [Website Optimization](http://www.websiteoptimization.com/)
- [Performance Rules](http://developer.yahoo.com/performance/rules.html)
- [Page Speed](https://developers.google.com/speed/pagespeed/)
- [Paint Flashing Tool](https://developer.mozilla.org/en-US/docs/Tools/Paint_Flashing_Tool)

#### DOCUMENT & WEBSITE STRUCTURE

It is important to be semantically correct because blind people and disabled
people accessing your website will make up 8% of the world population (1/12 men
and 1/200 women)

1. Header `<header>`
2. Navigation Bar `<nav>`

   - Keep separate from header because better for accessibility as screen
     readers can read the 2 features better

3. Main Content `<main>, <article>, <section>, <div>`
4. Sidebar `<aside>`
5. Footer `<footer>`

#### HTML SEMANTICS

- Make sure to use the correct element
- Semantic values are used by search elements and screen readers
- Ideally can create the same feel with using CSS, but will lose out on above
  benefits

#### HTML VALIDATION

- Run HTML page through **Markup Validation Service**
- Gives you a report and tells you what's wrong with your HTML

#### ANALYZING HTML

```HTML
<!DOCTYPE html>

- Cared about this in the past
- Use to be used for setting the rules
- Used for parsing and let's the web know what version is being used
```

```HTML
<html></html> A.K.A the root element
```

```HTML
<head></head>

- Everything you want to include that is not going to be seen, meta information
- Ex. keywords/page description for searching and SEO
```

```HTML
<meta charset="utf-8">

Character set uses utf-8 which has most characters in many languages
```

```HTML
<title></title> Appears in the browser page tab
```

```HTML
<body></body> All content page viewers will see
```

```HTML
<img src="image.jpg" alt="placeholder for image">

- alt="test" will show the text, this will be used if the image can't be
  displayed or a screen reader will read what is on the screen for people with
  disabilities
```

```HTML
<link> Elements always go inside the **HEAD** of the document
```

```HTML
<script></script>

- Better to put at the BOTTOM of the document body right before </body>
  because it will ensure that all HTML content has been read by the browser before
  it tries to apply JavaScript to it
- If JavaScript tries to access an element that doesn't exist yet, the browser
  will throw an error
```

```HTML
<dl></dl>
<dt></dt>
<dd></dd>

- Description lists
- Mark up a set of items and their associated descriptions, such as terms and
  definitions, questions, and answers
```

```HTML
<blockquote></blockquote> Indents text like in a indented paragraph
```

```HTML
<q></q> "Like this"
```

```HTML
<p><cite>Think and Grow Rich</cite></p> by Napoleon Hill

Italicizes a citation, in this example the book title
```

```HTML
<abbr title="Hyper Text Markup Language">HTML</abbr>

When you hover over HTML, the full text of Hyper Text Markup Language shows
```

```HTML
<address></address> Will appear italicized of who wrote the markup
```

```HTML
<sup></sup> Superscript, 26th the "th" will be raised
<sub></sub> Subscript, h20, the "2" will be lowered
```

```HTML
<code></code> Code
<samp></samp> Sample
<kbd></kbd> Keyboard Keys
<var></var> variables for math
```

- These all look the same, but it is more for the users experience

```HTML
<pre></pre> Preserves both spaces and line breaks
```

```HTML
<time></time>
- Encodes data and times in machine readable way
- Events to calendars
- Search engines can provide smarter search results
```

#### HTML LAYOUT ELEMENTS

```HTML
<main></main> Unique, one per page and goes inside the body
```

```HTML
<article></article> Block of related content that makes sense on its own
```

```HTML
<section></section> Groups together for single page functionality
```

```HTML
<aside></aside> Content not directly related to main content, indirect info
```

```HTML
<header></header> Introductory content
```

```HTML
<nav></nav> Navigation for that page
```

```HTML
<footer></footer> Represents a group of end content
```

#### HTML MULTIMEDIA

- Don't alter the size of an image using HTML
- If you do need to alter a size, do it in CSS
- Can add title to an image when hovered over
- If an image has meaning, in terms of your content, you should use `<img>`
  If an image is purely decoration, you can use CSS

#### HTML VIDEO FEATURES

```HTML
<video></video>

Attributes:
width and height: set the width and height
autoplay: automatically plays the video
loop: loops the video
muted: plays but muted
poster: used for ads
preload: used for buffering large files
```

#### EMBEDDING TECHNOLOGIES

```HTML
<iframe></iframe>

- Designed to allow you to embed other web documents into the current document
- Ex. YouTube or Google Maps

Attributes:
allowfullscreen
frameborder
src: Good idea to set src with JavaScript for optimization
```

**Security**:

- Click Jacking: iframe attack
- Use HTTPS: encrypts version of HTTP
- Use sandbox attribute: limits what people can do

#### VECTOR GRAPHICS (SVG)

- Difference between `.png` and `.svg`
- `png` is more pixilated when zooming in because it contains information on
  where each pixel could be
- `svg` uses algorithms to be crisp when image is responding to screen size

#### RESPONSIVE IMAGES

- **Resolution Switching**
  - Problem: Want to display identical image content, just larger or smaller
    depending on the device
- **Solution**: Use srcset and sizes
- **srcset**: Defines the set of images we will allow the browser to choose
  between and what size each image is
- **sizes**: Defines a set of media conditions (screen widths) and indicates
  which image size to use when certain media conditions are true

#### HTML FORMS

```HTML
<form action="/my-handle-form" method="post"></form>

Attributes:
action: where to send data
method: http verb
```

#### FORM VALIDATION

1. Get data in correct format
2. Protect user's accounts, make them create good passwords
3. Protect ourselves from fraud

2 Types of Form Validation:

1. **Client-Side Validation**:
   - Occurs in the browser before submitted to the server
   - JavaScript Validation (customizable)
   - Built-In Form Validation (HTML5)
2. **Server-Side Validation**:
   - After data has been submitted, done before data is saved in DB
   - Last line of defense for validation

#### HTML5 FORM VALIDATION

Attributes:

- required
- regex
- minlength: for characters
- maxlength: for characters

#### FAST CODING HTML PAGES (OPTIMIZATION)

1. Reduce Page Weight
   - **Minimization**:
     - Remove whitespace and comments
     - Move inline script and CSS to external files
2. Minimize Number of Files
   - Reduce number of files referenced which will result in less HTTP calls
3. Use a Content Delivery Network (CDN)
   - Reduce the physical distance between your server and your visitor
   - CDNs store cached versions of your website and reduces latency (the amount
     of time it takes to travel)
4. Reduce Domain Lookups
   - Each separate domain costs time to lookup in DNS lookup, so use minimum
     number of domain lookups
5. Cache Reused Content
   - Look into how this is done in the header "last modified"
6. Optimally order components of a page
   - Load HTML before JavaScript
   - JavaScript scripts are placed at the bottom right before `</body>` closes!
7. Reduce Number of Inline Scripts
   - These are expensive because the parser must assume that in an inline script
     could modify the page structure
8. Use Modern CSS and Valid Markup
   - CSS reduces the amount of markup
9. Don't Use Tables for Layouts
   - Use flex box
   - CSS flexible box layout
   - CSS Grid layout
10. Minify & Compress SVG Assets & Images
    - Do in Photo Shop or compress jpeg & tiny png
