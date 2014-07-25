---

layout: post
title:  "Super-intuitive UI for Likert and Matrix Survey Questions in Insightify"
date:   2014-06-09 16:35:54
categories: experiments
excerpt: <p class="postdesc">A Likert scale is a bipolar scaling method, measuring either a positive or negative response to a statement. Often five ordered response leverls are used, but some researchers use seven and even nine levels—it's been found that using seven or nine levels produce higher mean scores.</p>

---

<h2>Background</h2>
<p>A Likert Scale question, named after its inventor Rensis Likert is basically a <strong>rating scale</strong> (although there are quite a lot of differences)</p>

<p>The format of a typical five-level Likert item, for example, could be:</p>

* Strongly disagree
* Disagree
* Neither agree nor disagree
* Agree
* Strongly agree



<img src="/images/survey.png" alt="Alfred App Screenshot" style="float:left" />
<div><p class="caption">A Likert Scale question in a matrix form</p></div>
<p>A Likert scale is a bipolar scaling method, measuring either a positive or negative response to a statement. Often five ordered response levels are used, but some researchers use seven and even nine levels—it's been found that using seven or nine levels produce higher mean scores.</p>

<p>Creating surveys with Insightify is as easy as taking a survey. Its super-intuitive design gives user a WYSIWYG interface to create surveys. It was fun creating the simpler question types like Single/Multiple selection, Date question etc. even if they were mostly forms. Then we moved to the next sprint: on the Likert Scale questions. It was a real challenge to keep the ease of use and intuitiveness we just built!.</p>

<h2>How do we do this?!</h2>
<p>Stuck with this, there was only one thing in our minds for the coming days even while we were sleeping.</p>
<img src="/images/IMG_4805.jpg" alt="" style="float:left" />
<div><p class="caption"></p></div>
<p>This was at a point where we thought we almost figured it out. But soon we realized we need Likert Scale questions' 'baap'— Likert Scale questions as a matrix of choices. It's important to follow the same design language for both these types of questions. One more challenge here - survey creators should be able to choose multiple answers to the question, in addition to the single choice. Think checkboxes and radio buttons.</p>
<p>Well, matrix of choices can be given as a matrix of dropboxes too. But e decided we won't do dropdowns. It drives the respondent crazy if given a matrix with dropdowns. One dropdown itself is evil.</p>

<img src="/images/IMG_4806.JPG" alt="" style="float:left" />
<div><p class="caption">It was shit, and we knew it.</p></div>
<p>Voila! We came up with the most confusing user interface ever!</p>
<p>Then again, one day I had a faint spark of an idea and I asked Niket, our JS/Rails guru whether we can have drag handles in these questions. He said we can have anything if it means a better experience. We sat together and came up with a prototype - An drag-expandble Likert Scale question.</p>
<img src="/images/IMG_4807.JPG" alt="" style="float:left" />
<div><p class="caption">Sketch: Drag-expandable Likert Scale</p></div>
The major benefit of this interface was that it was scalable, and the matrix is just an extension to the Likert Scale interface.

<img src="/images/IMG_4808.JPG" alt="" style="float:left" />
<div><p class="caption">Winner!</p></div>
It was a wow moment for all of us. We added keyboard shortcuts, tab focus, drag back to remove columns/rows. Hitting return from the last column of the last row in the matrix would spawn another row, too. It was fantastic.

<p>Oh, to switch between multiple choice (checkboxes) array and single choice (radio buttons), we just gave two links at the top of the matrix :)</p>

<p>See it working in the video below!</p>
<iframe width="800" height="600" src="//www.youtube.com/embed/yhcohNvZuOc?rel=0" frameborder="0" allowfullscreen></iframe>