---

layout: post
title:  "CSS3 and SASS — Best Practices and Guidelines"
date:   2013-09-01 16:35:54
categories: experiments
excerpt: <p class="postdesc">Use valid CSS where possible. Unless dealing with CSS validator bugs or requiring proprietary syntax, use valid CSS code. Place comments on a new line above their subject</p>

---

### General Rules

+ Use valid CSS where possible
+ Unless dealing with CSS validator bugs or requiring proprietary syntax, use valid CSS code
+ Place comments on a new line above their subject
+ Keep line-length to 80 columns

### Readability

+ Use one discrete selector per line in multi-selector rulesets.
+ Include a single space before the opening brace of a ruleset.
+ Include one declaration per line in a declaration block.
+ Use one level of indentation for each declaration.
+ Include a single space after the colon of a declaration.
+ Use lowercase and shorthand hex values, Example: `#aaa`
+ Use single or double quotes consistently. Prefer double quotes. Example: `content: ""`
+ Include a space after each comma in comma-separated property or function values.
+ Include a semi-colon at the end of the last declaration in a declaration block.
+ Place the closing brace of a ruleset in the **same** column as the first character of the ruleset.
+ Separate each ruleset by a blank line.

### Maintanability

+ Broad selectors allow us to be efficient, yet can have adverse consequences if not tested. Location-specific selectors can save us time, but will quickly lead to a cluttered stylesheet. **Exercise your best judgement** here.

+ Adding every new style you create onto the end of a single file would make finding things more difficult and would be very confusing for anybody else working on the project.

+ Use ID and class names that are as short as possible but as long as necessary.

### Numbers

+ Magic Numbers are unlucky. These are numbers that are used as quick fixes on a one-off basis. Example: `.box { margin-top: 37px }`
+ Line-heights should be a number—no units.
+ If the value of the width or height is 0, do not specify units. Example: `margin: 0`
+ Always quote attribute values in selectors  Example: `input[type="checkbox"]`


### Comments

+ Make liberal use of comments to break CSS code into discrete sections.
+ Use "sentence case" comments and consistent text indentation.
+ it is also useful to have a brief update log.

### Hacks and User Agent Detection

Avoid user agent detection as well as CSS hacks — try a different approach first. Giving detection and hacks a free pass will hurt projects in the long run as projects tend to take the way of least resistance. That is, allowing and making it easy to use detection and hacks means using detection and hacks more frequently—and more frequently is too frequently.

### File Organization
The CSS file organization should follow something like this:

    styles
    ├── components
    │   ├── comments.scss
    │   └── listings.scss
    ├── globals
    │   ├── browser_helpers.scss
    │   ├── responsive_helpers.scss
    │   ├── variables.scss
    ├── plugins
    │   ├── jquery.fancybox-1.3.4.css
    │   └── reset.scss
    ├── sections
    │   ├── issues.scss
    │   ├── profile.scss
    └── shared
        ├── forms.scss
        └── markdown.scss

### Other Formatting Guidelines

Large blocks of single declarations can use a slightly different, single-line format. In this case, a space should be included after the opening brace and before the closing brace.

    .selector-1 { width: 10%; }
    .selector-2 { width: 20%; }
    .selector-3 { width: 30%; }


Long, comma-separated property values - such as collections of gradients or shadows - can be arranged across multiple lines in an effort to improve readability and produce more useful diffs.


    .selector {
        background-image:
            linear-gradient(#fff, #ccc),
            linear-gradient(#f3c, #4ec);
        box-shadow:
            1px 1px 1px #000,
            2px 2px 1px 1px #ccc inset;
    }


### Use meaningful or generic ID and class names.

Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic. Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change. Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as “helpers.”

Using functional or generic names reduces the probability of unnecessary document or template changes.


    /* Nope: meaningless */
    #yee-1901 {}

    /* Nope: presentational */
    .button-green {}
    .clear {}
    /* YES! specific */
    #gallery {}
    #login {}
    .video {}
    /* YES! generic */
    .aux {}
    .alt {}

### Avoid qualifying ID and class names with type selectors.

Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.

Avoiding unnecessary ancestor selectors is useful for performance reasons. [Further Reading](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/)


    /* Nope */
    ul#example {}
    div.error {}

    /* YES! */
    #example {}
    .error {}


### Use 3 character hexadecimal notation where possible.

For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.

    /* Hmm.. */
    color: #eebbcc;

    /* Encouraged */
    color: #ebc;

### Use shorthand properties where possible.

CSS offers a variety of shorthand properties (like font) that should be used whenever possible, even in cases where only one value is explicitly set.

Using shorthand properties is useful for code efficiency and understandability.

    /* Not recommended */
    border-top-style: none;
    font-family: palatino, georgia, serif;
    font-size: 100%;
    line-height: 1.6;
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;

    /* Recommended */
    border-top: 0;
    font: 100%/1.6 palatino, georgia, serif;
    padding: 0 1em 2em;

### Separate words in ID and class names by a hyphen.

Do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.

    /* Nope: does not separate the words “demo” and “image” */
    .demoimage {}

    /* Nope: uses underscore instead of hyphen */
    .error_status {}

    /* YES! */
    #video-id {}
    .ads-sample {}

### SASS / SCSS & Specificity overload

Limit nesting to 3 level deep. Reassess any nesting more than 3 levels deep. This prevents overly-specific CSS selectors. If you find yourself going further, think about reorganising your rules (either the specificity needed, or the layout of the nesting)

   * Avoid large numbers of nested rules. Break them up when readability starts to be affected. Preference to avoid nesting that spreads over more than 20 lines.
   * Always place @extend statements on the first lines of a declaration block.
   * Where possible, group @include statements at the top of a declaration block, after any @extendstatements.
   * Consider prefixing custom functions with x- or another *namespace*. This helps to avoid any potential to confuse your function with a native CSS function, or to clash with functions from libraries.

<p></p>

    .selector-1 {
        @extend .other-rule;
        @include clearfix();
        @include box-sizing(border-box);
        width: x-grid-unit(1);
        // other declarations
    }

<p></p>
* Use a space between the last selector and the declaration block.
* Always use a single space between the last selector and the opening brace that begins the declaration block.
* The opening brace should be on the same line as the last selector in a given rule.

<p></p>

    /* Nope: missing space */
    #video{
      margin-top: 1em;
    }

    /* Nope: unnecessary line break */
    #video
    {
      margin-top: 1em;
    }

    /* YES! */
    #video {
      margin-top: 1em;
    }

### Separate selectors and declarations by new lines.

Always start a new line for each selector and declaration.


    /* Nope */
    a:focus, a:active {
      position: relative; top: 1px;
    }

    /* YES! */
    h1,
    h2,
    h3 {
      font-weight: normal;
      line-height: 1.2;
    }


### Separate rules by new lines.

Always put a blank line (two line breaks) between rules.


    html {
      background: #fff;
    }

    body {
      margin: auto;
      width: 50%;
    }


### Use single quotation marks for attribute selectors and property values.

Use single ('') rather than double ("") quotation marks for attribute selectors or property values. Do not use quotation marks in URI values (url()). Exception: If you do need to use the @charset rule, use double quotation marks—single quotation marks are not permitted.


    /* Nope */
    @import url("//www.google.com/css/maia.css");

    html {
      font-family: "open sans", arial, sans-serif;
    }

    /* YES! */
    @import url(//www.google.com/css/maia.css);

    html {
      font-family: 'open sans', arial, sans-serif;
    }


References:

* [GitHub](https://github.com/styleguide/css)
* [SMACSS](http://smacss.com/)
* [WordPress](http://make.wordpress.org/core/handbook/coding-standards/css/)
* [ThinkUp](https://github.com/ginatrapani/ThinkUp/wiki/Code-Style-Guide:-CSS)
* [Smashing Mag](http://coding.smashingmagazine.com/2008/05/02/improving-code-readability-with-css-styleguides/)
* [CSS Wizardry](http://csswizardry.com/2012/04/my-html-css-coding-style/)
* [Idiomatic](https://github.com/necolas/idiomatic-css)
