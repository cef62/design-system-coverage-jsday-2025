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

### We measure how much % of a page 
### is built with DS components.

::right::

<SlidevVideo autoplay autoreset='click'>
  <!-- Anything that can go in an HTML video element. -->
  <source src="./assets/slowmo1.mov" type="video/mp4" />
</SlidevVideo>

<!--
MISSING VIDEO BACKGROUND

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
