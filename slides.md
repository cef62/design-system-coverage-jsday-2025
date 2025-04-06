---
theme: seriph
background: ./assets/images/cover_01.jpeg
title: Design System Visual Coverage
class: text-center
drawings:
  persist: false
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# transition: slide-left
---

The story of how we measure the impact of our design systems in production!

# Design System Visual Coverage

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/preply/design-system-visual-coverage" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
Hi everyone!
This talk tells the story of how we measured the impact of our design systems directly in production through visual coverage.
All the code is Open Source and available on GitHub. The link is on the slides!
-->

---
layout: statement
---

# Why

### To measure the DS impact from a Product perspective

<!--
Let's start with a 1-min introduction before going into the project details.

First of all, why are we doing this? 

We needed a metric the leadership team could understand and use to compare the Design System investments with other initiatives.

So, we needed a metric that measures the DS impact from a product and user perspective, not a technical standpoint.
-->

---
layout: two-cols
---

# What

<br />

## We measure how much 
## % of a page is built
## with DS components. 

::right::

<SlidevVideo autoplay autoreset="click">
  <source src="/assets/videos/slowmo1.mov" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/assets/videos/slowmo1.mov">here</a>.
  </p>
</SlidevVideo>

<!--
We built a tool that measures how much a page is built with DS components.
You can briefly see it in action here, where we color the perimeters of DOM elements and calculate the overall DS impact in percentage.
-->

---
layout: statement
---

# How

### We calculate the coverage in users' devices 
### by using _idle callbacks_, _web workers_, and _typed arrays_ 
### without affecting the UX.

<!--
We used many tricks to optimize the CPU and memory performances so that we could run the DS visual coverage straight in production during user sessions without impacting their UX.

In this talk, we will discuss why, what, how, and how you can use our DS visual coverage on your product.
-->

---
layout: image-right
image: ./assets/images/stefano01.jpg
---

# Stefano Magni 
### Senior Front-end Engineer
#### [@Preply](https://preply.com/)

<br />
<br />


- [LinkedIn](https://www.linkedin.com/in/noriste/)
- [X](https://twitter.com/noriste)
- [Bluesky](https://bsky.app/profile/noriste.bsky.social)
- [GitHub](https://github.com/noriste)


---
layout: image-right
image: ./assets/images/matteo01.jpg
---

# Matteo Ronchi
### Frontend Architect
#### [@WorkWave](https://www.workwave.com/)

<br />
<br />


- [LinkedIn](https://www.linkedin.com/in/matteoronchi/)
- [X](https://twitter.com/cef62)
- [Bluesky](https://bsky.app/profile/cef62.bsky.social)
- [GitHub](https://github.com/cef62)

---
layout: intro
---

# WHY
#### Are we doing it

---
layout: image-left
image: ./assets/images/meeting_01_a.png
---

# Measuring Impact 
<br />

<v-clicks>

## Traditional Product Teams 
Measure the impact of their work through metrics like NPS, conversion rates..

## Design Teams
Lacks a metric to measure the impact of their work.

</v-clicks>

<!--
We work in DS teams, which are part of the Platform teams. 
One big difference between Platform teams and Product/Feature teams is how they measure the success of their work.
  - Product teams measure their work in conversions/revenues/money
  - And DS teams?...
--> 

---
layout: image-left
image: ./assets/images/meeting_01_a.png
---

# Static Analysis
<br />

<v-clicks>

- Measuring the impact of a change in the codebase
- Identifying the components most used 
- Identifying the components requiring the most maintenance 

- ## Those Metrics Are Not helping the leadership 

</v-clicks>

<!--
Usually, DS teams rely on static analysis. 
By Statically analyzing the codebases we can tell that our amazing button is used 1000 times... 

But this tells nothing to the leadership team! 
How are they supposed to be able to compare DS teams with other initiative? 
How can DS teams prove its value and asl for more investments?

We must be able to tell them how much % of the UI is built with the DS!
-->

---
layout: image-left
image: ./assets/images/meeting_01_b.png
---

# Visual Coverage
<br />

<v-clicks>

- Measuring the impact on specific pages
- Identifying the pages most impacted by the DS
- Provides metrics directly related to revenue and Company's goals
- Aligning with strategic objectives

</v-clicks>

---
layout: intro
---

# WHAT
#### Are we doing

---
layout: image-right
image: ./assets/images/brainstorming.jpeg
---

<v-clicks>

- It must be visual
- It must be easy to understand
- It must not be technical
- It must be independent from the Product teams

</v-clicks>

---
layout: center
---

# We could color DOM elements..

---
layout: center
---

# ..on the actual web page!

---
layout: image-right
image: ./assets/images/under-construction.jpeg
---

<v-clicks>

- Should we measure the usage of the DS tokens?
- Should we measure the usage of the DS components?
- Should we measure the usage of the DS patterns?
- What do we want to measure?
  - Areas
  - Borders
  - Or what?

</v-clicks>

---
layout: center
---

# We could draw lines around the components

---
layout: image-left
image: ./assets/images/draw-lines.jpeg
---

The visual coverage formula is:

```
green pixels / (green pixels + red pixels)
```
<br /> 

<v-clicks>

- It's a percentage value
- It directly measures what the user sees

</v-clicks>

---
layout: center
---

# The leadership team liked the idea!

---
layout: center
---

# But as we discovered...

---
layout: cover
background: ./assets/images/component-weight.png
---

# Not all the components' weights are the same


---
layout: image-left
image: ./assets/images/draw-lines.jpeg
---

<v-clicks>

- The coverage must express the impact on the user
- Components have different weights
- The weight of a component is subjective and unique per Product

</v-clicks>

---
layout: statement
---

# Better, but not enough!

---
layout: image-left
image: ./assets/images/draw-lines.jpeg
---

<v-clicks>

- ### Multiple teams can work on the same pages
- ### A page coverage must be calculated per team


</v-clicks>

---
layout: intro
---

# HOW
#### Are we doing it

---
layout: image-left
image: ./assets/images/wip.jpeg
---

# First attempt
<br />

<v-clicks>

- ### Parse the DOM
- ### Transform the DOM into a tree
- ### Transform the it into a bitmap
- ### Count the bitmap pixels

</v-clicks>

---
layout: image-left
image: ./assets/images/wip.jpeg
---

# Did it work?
<br />

<v-clicks>

- ### Yes!
- ### But it was slow
- ### It took up to 5 seconds on a high-end device...
- ### ...for a single page
- ### and it was blocking the main thread
- ### No way to run it on any CI pipeline

</v-clicks>

---
layout: intro
---

# What If...

<v-clicks>

# ...we change strategy?

</v-clicks>

---
layout: image-right
image: ./assets/images/change-of-strategy.png
---

# It may sound wild, but...
<br />

<v-clicks>

- ### If we make the process fast enough
- ### Without blocking the main thread
- ### We could run it in production
- ### Measure the coverage in real time 
- ### On the users' devices

</v-clicks>

---
layout: image-right
image: ./assets/images/wip.jpeg
---

# A few benefits
<br />

<v-clicks>

- Users navigate to all the pages (the CI covers mostly happy paths)
- Measuring what the users see aligns with the business goals
- More significant data set to collect
- <div class="text-2xl mt-8 mb-4 text-red">Unexpected bonus</div>
- Independence from the Product teams

</v-clicks>

---
src: ./pages/bitmap-animation.md 
---

---
layout: statement
---

# It's a two-steps process

---
layout: image-left
image: ./assets/images/wip.jpeg
---

# Analyze
<br />

<v-clicks>

- ### Traverse the DOM 
- ### Collect elements' size and position
- ### Detect which elements are part of the DS

</v-clicks>

---
layout: image-left
image: ./assets/images/wip.jpeg
---

# Optimize the parser
<br />

<v-clicks>

- ### Traverse using [Idle Callbacks](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback)
- ### The browser provides a time window to act
- ### The parser pause and resume as needed
- ### The parser accepts incomplete DOM trees

</v-clicks>

---
layout: image-right
image: ./assets/images/wip.jpeg
---

# Draw the bitmap
<br />

<v-clicks>

- ### Transform the parsed DOM into a bi-dimensional array
- ### The bitmap has the same size of the viewport
- ### Pixels are color-coded 
- ### The closest-to-the-user elements are drawn on top
- ### A component's weight affects the border thickness

</v-clicks>

---
layout: image-right
image: ./assets/images/wip.jpeg
---

# Bitmap Optimization
<br />

<v-clicks>

- ### Transform the parsed DOM into a bi-dimensional array
- ### The bitmap has the same size of the viewport
- ### Pixels are color-coded 
- ### The closest-to-the-user elements are drawn on top
- ### A component's weight affects the border thickness

</v-clicks>
