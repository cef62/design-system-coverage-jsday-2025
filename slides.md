---
theme: seriph
background: ./assets/images/cover_01.jpeg
title: Design System Visual Coverage
class: text-center
drawings:
  persist: false
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
exportFilename: design-coverage-jsday-2025
download: true
export:
  format: pdf
  dark: true
  withClicks: true
  withToc: false
favicon: 'https://cdn.jsdelivr.net/gh/slidevjs/slidev/assets/favicon.png'
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
- Provides metrics that can be included in a Company's goals
- Aligning with strategic objectives

</v-clicks>

<!--
How are they supposed to be able to compare DS teams with other initiative? 
How can DS teams prove its value and asl for more investments?

We must be able to tell them how much % of the UI is built with the DS!
-->

---
layout: intro
---

# WHAT
#### Are we doing

<!--
That's why we started thinking about coloring the DOM elements directly on the actual web pages.
We made some POCs: should we measure the usage of the DS tokens? Of the DS components? Should we measure components' areas? perimeters?
-->

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


<!--
We decided to count the elements' borders, 
the visual coverage formula is 

`green pixels / (green pixels + red pixels)`

This gives us a 0-100%, and directly measures what the users see.
The leadership team liked the idea.
-->


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


<!--
Then we evolved it. 
Made the visual coverage more meaningful in terms of expressing the DS impact on the users. 
The components must have different weights because their impact on the UI/UX/accessibility is different. 

This is a manual and subjective process, and it really depends on the Product.
-->


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


<!--
Then we needed to split pages by teams, because some pages can be owned by multiple Product teams. 

This is fundamental to identify DS usage issues, and allow Product teams to have a dedicated DS visual coverage percentage, and they can also use it to set their quarterly ORKs.
-->

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

- ### Color the borders via CSS
- ### Transform DOM into a PNG
- ### Count the pixels

</v-clicks>

<!--
The initial implementation was quite conventional. 
We were converting the whole page to a png and then count the pixels. 
-->

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

<!--
This was a big performance bottleneck. 
A big page required something like 5 seconds on a high-end device. 
This was a challenge also for CI pipelines! 
Calculating the coverage at the end of e2e tests would have costed too much.
-->

---
layout: intro
---

# What If...

<v-clicks>

# ...we change strategy?

</v-clicks>

<!--
We could make it faster and run it in CI pipelines... 
Or we could make it even faster and run it... 
in production, during users' sessions, on their device!
-->

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

<!--
Sounds like a crazy idea? Think about it!
-->

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


<!--
1. Users use all the pages (while E2E tests cover just the happy paths)
2. Measuring the DS impact on what users's see is 100% aligned with the idea of measuring the impact from a Product perspective!
3. There's also another huge convenience: by installing it at the root of the website, the DS team was independent! Mot of the times, Platform teams's initiatives depend on Product teams' help, but Product teams are always busy with their OKRs. So being independent is a huge benefit for us.
-->

---
src: ./pages/bitmap-animation.md 
---

---
layout: statement
---

# It's a two-steps process

<!-- 
Let's look at how we implemented it.
The DS visual coverage is made of two steps:
1. Parsing the whole DOM tree to collect element's sizes, and to detect which are generated by DS components
2. Transforming this tree into a bitmap to calculate the coverage
-->

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

<!--
Parsing the DOM safely rely on idle callbacks. 

This is the idea:
1. The browser tells us when it's idle, and how many remaining milliseconds we have
2. We pause and resume parsing the DOM tree
3. Sometimes we could calculate the coverage on Frankenstein pages (imagine starting to measure it on a page with an opened modal, and then finishing it when the modal doesn't exist anymore), but on big numbers, this is irrelevant, the only important thing is to leave the UX untouched
-->

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

<!--
Regarding the bitmap:
1. We generate a bi-dimensional array that represents the page, with the same screen width and height
2. We set different "colors" for the "pixels". This is necessary to mimic (even if it's not perfect) the CSS depth logics and count the closest-to-the-user elements
3. Then we count the pixels
-->

---
layout: image-right
image: ./assets/images/wip.jpeg
---

# Bitmap Optimization
<br />

<v-clicks>

- ### We got help from an expert: **Massimiliano Mantione**
- ### Transform the array to be mono-dimensional
- ### Switch to `Typed Arrays`
- ### Make the code branch-free, removing most conditional statements
- ### Run the bitmap drawing in a [Web Worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)

</v-clicks>

<!--
We involved Massimiliano Mantione 
Yes the one who talked yesterday about the cost of abstractions, who is a former Google Chrome engineer, to help us optimizing the performances even more. 
Thanks to his suggestions:
1. The array is not bi-dimensional anymore. A mono-dimensional array optimizes accessing the memory, because there's just one step to find the pixel, instead of two
2. We use typed arrays to reduce the memory footprint
3. We refactored our code to be branch-free as much as possible: removing branches (if conditions) allows V8 to translate JS almost to C++, with all the performance benefits.
-->

---
layout: statement
---

# This is all great, but...

<v-clicks>

# ...show me the numbers!

</v-clicks>

---
layout: image-right
image: ./assets/images/wip.jpeg
---

<v-clicks>

- ### <div class="mb-10">❌ The initial implementation took `5 blocking seconds` </div>
- ### <div class="mb-10">🚧 The first bitmap-based version took `50 blocking ms`, and `30MB` of memory </div>
- ### <div class="mb-14">✅ The final version took `35 non-blocking ms`, and `0.3 MB` of memory </div>
- ### ℹ *The Huawei P9 takes `900 non-blocking ms` on a big page*

</v-clicks>

---
layout: statement
---

# Was it worth it?

---
layout: image-right
image: ./assets/images/wip.jpeg
---

# Yes!  
<br />

<v-clicks>

- ### <div class="mb-10">It run in production</div>
- ### <div class="mb-10">It gives real time data</div>
- ### <div class="mb-10">It provides great insights for the Leadership</div>

</v-clicks>

<!--
Were all this efforts needed? Yes! 

During the initial tests, when the code wasn't so optimized, we released the visual coverage to just 1% of the users and 1 of them reported 400 blocking ms 
This isn't acceptable for a brand that wants to offer the bet possible UX. 

Let's look at it working on Preply.com: for the sake of debugging, some of the DS coverage APIs can be triggered straight from the browser's console. 

Here you can see, for example, that on my student's home page, the coverage is... 
and there are two different containers (containers are part of the pag assigned to different teams)
if I go to the search page, the coverage is...

And given it doesn't impact the UX, on Preply we calculate it every 10 minutes on all users connected to our website. 

And we built this dashboard where we can show the company the overall average. 

But, from a DS team perspective, we care more about the coverage per teams and how it goes over time, and the coverage per page.
-->

---
layout: default
---

# Advantages
<br />

<v-clicks>

- ### <div class="mb-4">It can run on any web application</div>
- ### <div class="mb-4">**Preply** and **WorkWave** use it already</div>
- ### <div class="mb-2">It's configurable</div>
  - ### <div class="mb-2">You are responsible to identify the DS components</div>
  - ### <div class="mb-4">You are responsible to set the components' weight</div>
- ### <div class="mb-4">You can split the page into different containers</div>
- ### <div class="mb-4 text-green">It's Open Source</div>

</v-clicks>

---
layout: default
---

# Things to consider
<br />

<v-clicks>

- ### <div class="mb-4">Collecting data in production comes with some cost</div>
- ### <div class="mb-4">The coverage data change over-time *(thinks of the stock market)* </div>
- ### <div class="mb-4">It complements static analysis</div>
- ### <div class="mb-2">It's a monitoring metric</div>
  - ### <div class="mb-4">You can check the trends only after publishing a page</div>

</v-clicks>

---
layout: default
---

# The progress so far
<br />

<v-clicks>

- ### <div class="mb-4">✅ Preply battle tested in production (1+ year)</div>
- ### <div class="mb-4">✅ Detailed articles: [here](https://dev.to/noriste/visual-coverage-why-and-how-preply-measures-the-impact-of-the-design-system-part-i-3omb) and [here](https://dev.to/noriste/the-implementation-details-of-preplys-design-system-visual-coverage-part-ii-1ao2)</div>
- ### <div class="mb-4">✅ Open Source the project –[GitHub](https://github.com/preply/design-system-visual-coverage)</div>
- ### <div class="mb-4">🚧 Implementing a devtool</div>
- ### <div class="mb-4">🚧 Scaling it at WorkWave</div>
- ### <div class="mb-4">🚧 Helping Docplanner and Monday.com to adopt it</div>

</v-clicks>

---
layout: statement
---

## Feedback
<br />

<div style="display: flex; justify-content: center; align-items: center; flex-direction: column; gap: 1rem;">
  <img src="./assets/qrcode.png" width="30%" />
</div>

[grusp.org/agenda](https://grusp.org/agenda)
