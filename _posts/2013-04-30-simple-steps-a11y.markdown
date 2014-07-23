---
layout: post
title:  "Simple Steps to build Accessible Websites"
date:   2013-04-30 16:35:54
categories: experiments
---

Accessible Design” means design that includes the needs of people whose physical, mental, or environmental conditions limit their performance. Building an accessible website is important for people who do not have any of these physical or mental characteristics too, as it increases speed, decreases errors and reduces the learning curve for all users. Here you can read everything you would need to build an accessible website, in a simplified format.

## Principles

These four principles are the foundation of web accessibility. Without any one of these principles access will be limited for some people.

* ### Perceivable
Information and user interface components must be presentable to users in ways they can perceive.

* ### Operable
User interface components and navigation must be operable.

* ###  Understandable
Information and the operation of user interface must be understandable.

* ### Robust
Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.


### Text Alternatives

Provide text alternatives for any non-text content so that it can be changed into other forms people need.

### Time-based Media

Provide alternatives for time-based media. (Pre-recorded)

  * Provide captions
  * Provide audio transcript

### Adaptable

Create content that can be presented in different ways (for example simpler layout) without losing information or structure.

* Write semantic HTML and make sure the three layers viz markup, styling, scripting are separate

### Distinguishable

Make it easier for users to see and hear content including separating foreground from background.

* Make sure your content vs. background has a contrast ratio of *atleast 4.5:1*
* Make sure the text can be resized upto double its original value (without loss of content/functionality) without assistive technology.
* If any audio on a Web page plays automatically for more than 3 seconds, user should be able to control the volume and should be able to play/pause

### Keyboard Accessible

Make all functionality available from a keyboard.

* All functionality of the content is operable through a keyboard interface without requiring specific timings for individual keystrokes

### Enough Time

Provide users enough time to read and use content.

* Putting it simple: Avoid moving, blinking, scrolling or auto-updating information. If doing so, [refer](http://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits.html)

### Seizures

Do not design content in a way that is known to cause seizures

* Web pages should not contain anything that flashes more than three times in any one second period

### Navigable

 Provide ways to help users navigate, find content, and determine where they are.

* Provide skip-to-content links to bypass blocks of content that are repeated on multiple pages.
Web pages should have titles that describe topic or purpose
* Give  focus to content in an order that preserves meaning and operability.
* The purpose of each link should be determined from the link text alone or from the link text together with its programmatically determined link context
* More than one way should be available to locate a Web page within a set of Web pages except where the Web Page is the result of, or a step in, a process.
* Headings and Labels: Headings and labels should describe topic or purpose.
* Focus should be visible: Any keyboard operable user interface should have a mode of operation where the keyboard focus indicator is visible.

### Readable

Make text content readable and understandable.

* The Default language of each Web page should be able to be programmatically determined.

### Predictable

Make Web pages appear and operate in predictable ways.

* When any component receives focus, it should not initiate a change of context.
* Use consistent navigation
* Components that have the same functionality within a set of Web pages should be identified consistently.

### Input Assistance
Help users avoid and correct mistakes

* Labels or instructions should be provided when content requires user input.
* If an input error is automatically detected, the item that is in error is identified and the error is described to the user in text. (Form validations)
* If an input error is automatically detected and suggestions for correction are known, then the suggestions should be provided to the user.
* Make sure that data entered by the user is checked for input errors and the user is provided an opportunity to correct them.
* A mechanism should be available for reviewing, confirming, and correcting information before finalising the submission.

### Compatible

Maximize compatibility with current and future user agents, including assistive technologies.

* Make sure:
    + Elements have complete start and end tags
    + elements are nested according to their specifications
    + elements do not contain duplicate attributes
    + Any IDs are unique
* For all user interface components (eg:form elements, links and components generated by scripts) the name and role should be able to be determined programmatically.


## Conformance (Level AA)

* Level AA: For Level AA conformance, the Web page satisfies all the Level A and Level AA Success Criteria, or a Level AA conforming alternate version is provided.

* Conformance (and conformance level) is for full Web page(s) only, and cannot be achieved if part of a Web page is excluded.

* Conformance is not possible at a particular level if any page in the process does not conform at that level or better.

* Only accessibility-supported ways of using technologies are relied upon to satisfy the success criteria.

* If technologies are used in a way that is not accessibility supported, or if they are used in a non-conforming way, then they do not block the ability of users to access the rest of the page.

* In addition, the following success criteria apply to all content on the page, including content that is not otherwise relied upon to meet conformance, because failure to meet them could interfere with any use of the page:

    + Audio Control
    + No Keyboard Trap
    + Three Flashes or Below Threshold
    + Pause, Stop, Hide

##### Note: These are just simplified and general guidelines to be kept in mind while building a webpage. Go through W3.org's WCAG20, follow *thorough* procedures and tools for making the site accessible.

[Web Content Accessibility Guidelines (WCAG) 2.0](http://www.w3.org/TR/WCAG20/)
