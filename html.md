This page outlines the style guide for HTML pages in all Mozpacers projects.

## Linting

Use [grunt-html](https://www.npmjs.com/package/grunt-html) to detect errors and potential problems.

## Spacing

In general, the Mozpacers style guide encourages liberal spacing for improved human readability.

- Indentation with two spaces.
- Don't indent the direct children of `html`, `body`, `script`, or `style`.Indent everything else.
- No whitespace at the end of line or on blank lines.
- Unix-style linebreaks ('\n'), not Windows-style ('\r\n').
- Separate attributes with a space.
- The line length should be no more than 80 characters.


```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Sample Page</title>

  <link rel="stylesheet" href="/style.css">
  <style>
  body {
    font-size: 100em;
  }
  </style>

  <script src="/mozpacers.js"></script>
  <script>
  $(function() {
    $("p").text($.fn.mozpacers);
  });
  </script>
</head>
<body>

<section>
  <p>Mozilla is awesome!<p>
</section>

</body>
</html>
```

## Formatting

 - Always use the minimal, versionless and lowercase doctype.
 - Always define which language the page is written in.
 - Always include `html`, `head`, and `body` tags.
 - Always define the character encoding. Most pages should use utf-8. The encoding should be defined as early as possible and must be in the [first 1024 bytes of the document](https://html.spec.whatwg.org/multipage/semantics.html#charset).
 - Always use lowercase names for elements and attributes.
 - Always quote attribute values. Always use double quotes instead of single quotes.
 - Include the optional closing tags.
 - Self-closing elements must not be closed.
 - Optional attributes must be omitted.
 - `rel`, `type`, `src`, `href` and `class` attributes must be written before any other attribute.
 - Always include an `alt` attribute for images.

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Good Example</title>
  <link rel="stylesheet" href="style.css">
  <script src="/mozpacers.js"></script>
</head>
<body>

<img class="sample-image" src="assets/img/img.png" alt="Sample Image">
<p>This is a sample image</p>

</body>
</html>
```

## HTML Semantics

Always use HTML elements for what they are meant to be used for.

## Reducing Markup

Always try to avoid superfluous parent elements.

```html
<!-- Bad HTML -->
<span class="avatar">
  <img src="assets/img/img.png" alt="Jane Doe">
</span>

<!-- Good HTML -->
<img class="avatar" src="assets/img/img.png" alt="Jane Doe">
```

## Separation of Concerns

Always keep markup, styling, and scripting separate.

```html
<!-- Bad Example -->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Sample Page</title>
  <script src="script.js"></script>
</head>
<body>

<h1 style="font-size:1em;line-height:2em;">This is a heading.</h1>
<p style="text-decoration:underline;font-size:.5em;line-height:1em;">This is an underlined paragraph.</p>
</body>
</html>

<!-- Good Example -->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Sample Page</title>
  <link rel="stylesheet" href="style.css">
  <script src="script.js"></script>
</head>
<body>

<h1>This is a heading.</h1>
<p>This is an underlined paragraph.</p>
</body>
</html>
```

## Forms

Always include a `for` attribute for `label` elements. This is more robust than implicit labeling across browsers and assistive technologies.

```html
<!-- Bad Example -->
<label><input type="radio" name="input" value="first"> First</label>

<!-- Good Example -->
<input type="radio" name="input" id="input-1" value="first">
<label for="input-1">First</label>
```
Don't use the `placeholder` attribute for labeling; always use a `label`
 element.

```html
<!-- Bad Example -->
<input type="text" id="name" placeholder="Enter your name">

<!-- Good Example -->
<label for="name">Name</label>
<input id="name" type="text" placeholder="Jane Doe">
```

## Comments

Comments are always preceded by a blank line. Comments start with a capital first letter, but don't require a period at the end, unless you're writing full sentences. There must be a single space between the comment token and the comment text.

When comments take up multiple lines, break line after `<!--`, write your comment in multiple lines and then close the comment in a next line with `-->`.

```html
<!-- Good single line comment -->

<!--
Good example of a multi-line comment.
If your comment takes up multiple lines, please do this.
-->
```

**Proudly forked from [jQuery](https://github.com/jquery/contribute.jquery.org)**
