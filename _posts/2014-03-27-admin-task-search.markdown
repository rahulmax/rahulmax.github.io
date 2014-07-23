---

layout: post
title:  "Building the Admin Task Search"
date:   2014-03-27 16:35:54
categories: experiments
comments: true
excerpt: <p class="postdesc">One of the major pain points we had in EHQ Admin was the navigation. Adding/editing a tool or a widget was a pain. As more and more features were built into the app, it just became harder to get to certain common tasks.</p>

---
<p>One of the major pain points we had in EHQ Admin was the navigation. Adding/editing a tool or a widget was a pain. As more and more features were built into the app, it just became harder to get to certain common tasks.</p>

## Inspiration
<p>I’m a huge fan of Quicksilver and Alfred on OSX. The power it gives the user is unparalleled.</p>
<img src="/images/qs.png" alt="QuickSilver Screenshot" style="float:left" />
<div><p class="caption">A screenshot of Quicksilver</p></div>

<img src="/images/alfred.png" alt="Alfred App Screenshot" style="float:left" />
<div><p class="caption">A screenshot of Alfred App</p></div>

I love github’s find files interface (which incorporated the programmer-intuitive ⌘+T onto its web interface). Made popular by Textmate, the Command/Control + T Go-To-File has been in use by programmers since years. Here's a screenshot from Sublime Text's ⌘+T interface:
<img src="/images/sublime.png" alt="Sublime Text's ⌘+T Interface Screenshot" style="float:left" />
<div><p class="caption">Sublime Text's ⌘+T Interface Screenshot</p></div>

Another awesome feature which caught my eye was Atlassian Jira’s Dot ‘.’ and Comma ‘,’ Shortcuts which pops out a search box and common tasks which lets you type a task.

<img src="/images/jira.png" alt="Jira DOT Interface" style="float:left" />
<div><p class="caption">Jira DOT Interface</p></div>

## Observation and Interview

First thing we did was study user patterns. What are the tools they use in EHQ, How they navigate to a tool/widget and add them. We set up a demo site and asked people to create a website from scratch. Most of them said if there was a shortcut to get to where they wanted to, it would’ve reduced their time to almost half. Having shortcuts listed in the site itself would become a long, un-trackable list of links. Searchable list seemed like a good idea but placing it near a widget would make it just another widget. We wanted something which would be accessible site-wide.

## Brainstorming and Prototyping

We did brainstorming on the idea and came up with tons of features to be incorporated. It had the capability for switching between projects, adding, editing deleting stuff, manage settings etc.

One of the first prototype paper sketches:

XXX

We proposed a couple of UI options.
<img src="/images/adminsearch.png" alt="Admin Task Search" style="float:left" />
<div><p class="caption">UI For Admin Task Search: This one was discarded as it interrupts the user from changing his mind, and since lightboxes are considered to hinder accessibility.</p></div>
Then, we came up with this:
<img src="/images/adminsearch1.jpg" alt="Admin Task Search" style="float:left" />
<div><p class="caption"></p></div>

Finally keyboard shortcuts and keyboard navigation were built-in. Check out the video to see it in action.

<iframe width="800" height="600" src="//www.youtube.com/embed/CTFY1owAHnQ?rel=0" frameborder="0" allowfullscreen></iframe>