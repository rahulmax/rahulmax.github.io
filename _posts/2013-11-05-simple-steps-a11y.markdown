---
layout: post
title:  "Simple Steps to build Accessible Websites"
date:   2014-03-27 16:35:54
categories: experiments
---


---

### General Guidelines

##### Be consistent.
##### Styleguides are helpful if and only if they are used properly. Remove every styleguide which doesn’t effectively help you to get a better understanding of the code or achieve a well-structured code.

+ Take a few minutes to look at the code around you and determine its style.

+ The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you’re saying rather than on how you’re saying it.

+ Explain code as needed, where possible.

+ Use comments to explain code: What does it cover, what purpose does it serve, why is respective solution used or preferred.
+ Use 2 white spaces for indentation. No tabs.
+ All code in the code-base should look like a single person typed it, even when many people are contributing to it.

---

### HTML5 (HTML syntax) is preferred for all HTML documents: `<!DOCTYPE html>`

It’s recommended to use HTML, as text/html. Do not use XHTML. XHTML, as application/xhtml+xml, lacks both browser and infrastructure support and offers less room for optimisation than HTML.

No need to close void elements, i.e. write `<br>`, not `<br />` [Refer w3.org](http://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag)

### Use valid HTML code always

+ Use W3C HTML validator to test. Using valid HTML is a measurable baseline quality attribute that contributes to learning about technical requirements and constraints, and that ensures proper HTML usage.

+ Use elements for what they have been created for, keeping semantics in mind. Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.

### Provide alternative contents for multimedia

+ For multimedia, such as images, videos, animated objects via canvas, make sure to offer alternative access. For images that means use of meaningful alternative text `alt` and for video and audio transcripts and captions, if available.

```
    <!-- Nope -->
    <img src="homepageui.png">

    <!-- Yes -->
    <img src="spreadsheet.png" alt="Homepage design screenshot.”>
```

### Separate structure from presentation from behavior.

+ Strictly keep structure (markup), presentation (style), and behavior (script) apart, and try to keep the interaction between the three to an absolute minimum.

+ Make sure documents and templates contain only HTML and HTML that is solely serving structural purposes.

+ Move everything presentational into style sheets, and everything behavioural into scripts.
+ Keep the contact area as small as possible by linking as few style sheets and scripts as possible from documents and templates.
++ Separating structure from presentation from behavior is important for maintenance reasons. It is always more expensive to change HTML documents and templates than it is to update style sheets and scripts.

```
<!-- Nope -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!</center>

<!-- YES! -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first whatever site</h1>
<p>I’ve read about this on a few sites but today I’m actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.
<p>It’s awesome!

```


### Do not use entity references.

+ There is no need to use entity references like `&mdash;`, `&rdquo;`, or `&#x263a;`, assuming the same encoding (UTF-8) is used for files and editors as well as among teams.

+ The only exceptions apply to characters with special meaning in HTML (like < and &) as well as control or “invisible” characters (like no-break spaces).

```
<!-- Nope -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.

<!-- YES! -->
The currency symbol for the Euro is “€”.

```


### Omit the protocol portion (http, https etc.) from embedded resources.

+ Omit the protocol portion (http:, https:) from URLs pointing to images and other media files, style sheets, and scripts unless the respective files are not available over both protocols.

+ Omitting the protocol—which makes the URL relative—prevents mixed content issues and results in minor file size savings.

```
<!-- Nope -->
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>

<!-- Yes -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>

/* Nope */
.example {
  background: url(http://www.google.com/images/example);
}

/* YES! */
.example {
  background: url(//www.google.com/images/example);
}

```
### Omit type attributes for style sheets and scripts.

No need to use type attributes for style sheets (unless not using CSS) and scripts (unless not using JavaScript).

Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults. This can be safely done even for older browsers.

```
<!-- Nope -->
<link rel="stylesheet" href="//www.google.com/css/maia.css"
  type="text/css">

<!-- YES! -->
<link rel="stylesheet" href="//www.google.com/css/maia.css">

<!-- Nope -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"
  type="text/javascript"></script>

<!-- YES! -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```


### When quoting attributes values, use double quotation marks.

Use double ("") rather than single quotation marks ('') around attribute values.

```
<!-- Nope -->
<a class='button button-secondary'>Sign in</a>

<!-- YES! -->
<a class="button button-secondary">Sign in</a>
```
### Comments on closing tags

After every major chunk of HTML, for example, the end of a carousel, or the end of the content `<div>` place a closing-comment, for example:
```
<div class=content>
    ...
    <div class=carousel>
    ...
    </div><!-- /carousel -->
    ...
</div><!-- /content —>
```

### Mark todos and action items with TODO.

+ Highlight todos by using the keyword TODO only, not other common formats like @@.
+ Append a contact (username or mailing list) in parentheses as with the format TODO(contact).
+ Append action items after a colon as in TODO: action item.

```
<!-- TODO(rahulmax): revisit centering -->
<center>Test</center>

<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```

---

References:

* [GitHub](https://github.com/styleguide/css)
* [Google](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
* [W3](http://www.w3.org/TR/WCAG20/)
* [WordPress](http://make.wordpress.org/core/handbook/coding-standards/css/)
* [ThinkUp](https://github.com/ginatrapani/ThinkUp/wiki/Code-Style-Guide)
* [Smashing Mag](http://coding.smashingmagazine.com/2008/05/02/improving-code-readability-with-css-styleguides/)
* [CSS Wizardry](http://csswizardry.com/2012/04/my-html-css-coding-style/)
* [Idiomatic](https://github.com/necolas/idiomatic-css)
