---
theme: seriph
transition: none
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

<div class="text-white">The story of how we measure the impact of our design systems in production!</div>

# <div class="text-white">Design System <span class="text-red">Visual</span> Coverage</div>

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

## To measure the <span class="text-red">DS</span> impact from a <span class="text-red">Product</span> perspective

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

<SlidevVideo autoplay autoreset="slide" controls>
  <source src="/assets/videos/slowmo2.mov" type="video/mp4" />
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
### by using <span class="text-red">_idle callbacks_</span>, <span class="text-red">_web workers_</span>, and <span class="text-red">_typed arrays_</span> 
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
### <div class="text-orange">Senior Front-end Engineer</div>
### <div class="text-orange">Design System Tech Lead</div>
#### [@Preply](https://preply.com/)

<br /><br /><br /><br />
<br /><br /><br /><br />

- [<span class="text-gray">linkedin/</span>noriste](https://www.linkedin.com/in/noriste/)
- [<span class="text-gray">x.com/</span>noriste](https://x.com/noriste)
- [<span class="text-gray">bsky.app/</span>noriste.bsky.social](https://bsky.app/profile/noriste.bsky.social)
- [<span class="text-gray">github/</span>noriste](https://github.com/noriste)

---
layout: image-right
image: ./assets/images/matteo01.jpg
---

# Matteo Ronchi
### <div class="text-orange">Frontend Architect</div>
#### [@WorkWave](https://www.workwave.com/)

<br /><br /><br /><br />
<br /><br /><br /><br />

- [<span class="text-gray">linkedin/</span>matteoronchi](https://www.linkedin.com/in/matteoronchi/)
- [<span class="text-gray">x.com/</span>cef62](https://x.com/cef62)
- [<span class="text-gray">bsky.app/</span>cef62.bsky.social](https://bsky.app/profile/cef62.bsky.social)
- [<span class="text-gray">github/</span>cef62](https://github.com/cef62)

---
layout: intro
---

# WHY
#### <div class="text-red">are we doing it?</div>

---
layout: image-left
image: ./assets/images2/meeting_01.png
---

# Measuring Impact 
<br />

<v-clicks>

### Product teams:
- We increased conversions by 10% 😍
- We saved 100K $ 😍
- Lifetime value increased by 1% 😍

### <div class="mt-10">DS team</div> 
- Our shiny button is used 176 times 😥🤔

</v-clicks>

<!--
We work in DS teams, which are part of the Platform teams. 
One big difference between Platform teams and Product/Feature teams is how they measure the success of their work.
  - Product teams measure their work in conversions/revenues/money
  - And DS teams?...
--> 

---
layout: image-left
image: ./assets/images2/meeting_02.png
---

# Measuring Impact 
<br />

### Product teams:
- We increased conversions by 10% 😍
- We saved 100K $ 😍
- Lifetime value increased by 1% 😍

### <div class="mt-10">DS team</div> 
- ~~Our shiny button is used 176 times~~ 🤔

<v-clicks>

- 40% of the UI is built with the DS 🤯👏

</v-clicks>



---
layout: image-left
image: ./assets/images2/static-analysis.jpeg
---

# Static Analysis
<br />

<v-clicks>

- ### <div class="mb-4">Measuring the <span class="text-red">impact</span> of a change in the codebase</div>
- ### <div class="mb-4">Identifying the components most used</div>
- ### <div class="mb-4">Identifying the components requiring the <span class="text-red">most maintenance</span></div>

- ## Those Metrics Are Not helping the leadership 

</v-clicks>

<!--
Usually, DS teams rely on static analysis. 
By Statically analyzing the codebases we can tell that our amazing button is used 1000 times... 

But this tells nothing to the leadership team! 
-->

---
layout: image-left
image: ./assets/images2/heat-map2.jpeg
---

# Visual Coverage
<br />

<v-clicks>

- ### <div class="mb-4">Measuring the impact on specific pages</div>
- ### <div class="mb-4">Identifying the pages <span class="text-red">most impacted</span> by the DS</div>
- ### <div class="mb-4">Provides metrics that can be included in a Company's goals</div>

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
#### <div class="text-red">are we doing</div>

<!--
That's why we started thinking about coloring the DOM elements directly on the actual web pages.
We made some POCs: should we measure the usage of the DS tokens? Of the DS components? Should we measure components' areas? perimeters?
-->

---
layout: image-right
image: ./assets/images/brainstorming.jpeg
---
# Requirements
<br /> 

<v-clicks>

- ### <div class="mb-4">It must be visual</div>
- ### <div class="mb-4">It must be <span class="text-red">easy</span> to understand</div>
- ### <div class="mb-4">It must not be technical</div>
- ### <div class="mb-4">It must be <span class="text-red">independent</span> from the Product teams</div>

</v-clicks>


---
layout: center
---

# We could <span class="text-red">color</span> DOM elements..

---
layout: center
---

# ..on the actual web page!

---
layout: image-right
image: ./assets/images2/mad-scientist.jpeg
---

<v-clicks>

- ### <div class="mb-4">Should we measure the usage of the <span class="text-red">DS tokens?</span></div>
- ### <div class="mb-4">Should we measure the usage of the <span class="text-red">DS components?</span></div>
- ### <div class="mb-2">What do we want to measure?</div>
  - ### <div class="mb-2">Areas</div>
  - ### <div class="mb-2 text-red">Borders</div>
  - ### <div class="mb-2">Or what?</div>

</v-clicks>

---
layout: center
---

# We decided to draw <span class="text-red">lines</span> around the components

---
layout: image-left
image: ./assets/images2/draw-lines1.png
---

### <div class="mb-4">The visual coverage formula is:</div>

```
green pixels / (green pixels + red pixels)
```
<br /> 

<v-clicks>

- ### <div class="mt-10 mb-4">It's a percentage value</div>
- ### <div class="mb-4">It directly measures what the user sees</div>

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

# The leadership team <span class="text-red">liked</span> the idea!

---
layout: center
---

# But as we discovered...

---
layout: cover
background: ./assets/images/component-weight.png
---

# Not all the components' <span class="text-red">weights</span> are the same


---
layout: image-left
image: ./assets/images2/draw-lines2.png
---

<v-clicks>

- ### <div class="mb-4">The coverage must express the <span class="text-red">impact</span> on the user (UI/UX/A11y)</div>
- ### <div class="mb-4">The weight of a component is <span class="text-red">subjective</span> and unique per <span class="text-red">Product</span></div>

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
image: ./assets/images2/draw-lines0.png
---

<v-clicks>

- ### <div class="mb-4">Multiple <span class="text-red">teams</span> can work on the same pages</div>
- ### <div class="mb-4">A page coverage must be calculated per <span class="text-red">team</span></div>


<!--
Then we needed to split pages by teams, because some pages can be owned by multiple Product teams. 

This is fundamental to identify DS usage issues, and allow Product teams to have a dedicated DS visual coverage percentage, and they can also use it to set their quarterly ORKs.
-->

</v-clicks>

---
layout: intro
---

# HOW
#### <span class="text-red">are we doing it</span>

---
layout: default
---

# First attempt
<br />

<v-clicks>

- ### <div class="mb-4">Color the <span class="text-red">borders</span> via CSS</div>
- ### <div class="mb-4">Transform DOM into a PNG</div>
- ### <div class="mb-4">Count the <span class="text-red">pixels</span></div>

</v-clicks>

<!--
The initial implementation was quite conventional. 
We were converting the whole page to a png and then count the pixels. 
-->

---
layout: default
---

# Did it work?
<br />

<v-clicks>

- ### <div class="mb-4">Yes!</div>
- ### <div class="mb-4">But it was slow</div>
- ### <div class="mb-4">It took up to <span class="text-red">5 seconds</span> on a high-end device...</div>
- ### <div class="mb-4">...for a single page</div>
- ### <div class="mb-4">and it was <span class="text-red">blocking</span> the main thread</div>
- ### <div class="mb-4">No way to run it on any CI pipeline</div>

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

# ...we change <span class="text-red">strategy</span>?

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

- ### <div class="mb-4">If we make the process <span class="text-red">fast enough</span></div>
- ### <div class="mb-4">Without blocking the main thread</div>  
- ### <div class="mb-4">We could run it in <span class="text-red">production</span></div>
- ### <div class="mb-4">Measure the coverage in <span class="text-red">real time</span></div> 
- ### <div class="mb-4">On the users' devices</div>

</v-clicks>

<!--
Sounds like a crazy idea? Think about it!
-->

---
layout: default
---

# A few benefits
<br />

<v-clicks>

- ### <div class="mb-4">Users navigate to all the pages (the E2E tests cover mostly happy paths)</div>
- ### <div class="mb-4">Measuring what the users see aligns with the <span class="text-red">business goals</span></div>
- ### <div class="mb-4">More significant data set to collect</div>
- ### <div class="mb-4"><div class="text-2xl text-red">Unexpected bonus</div></div>
- ### <div class="mb-4">Independence from the Product teams</div>

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

# It's a <span class="text-red">two-steps</span> process

<!-- 
Let's look at how we implemented it.
The DS visual coverage is made of two steps:
1. Parsing the whole DOM tree to collect element's sizes, and to detect which are generated by DS components
2. Transforming this tree into a bitmap to calculate the coverage
-->

---
layout: image-left
image: ./assets/images2/analyze.jpeg
---

# Analyze
<br />

<v-clicks>

- ### <div class="mb-4">Traverse the DOM </div>
- ### <div class="mb-4">Collect elements' size and position</div>
- ### <div class="mb-4">Detect which elements are part of the DS</div>

</v-clicks>

---
layout: image-left
image: ./assets/images2/optimize.jpeg
---

# Optimize the parser
<br />

<v-clicks>

- ### <div class="mb-4">Traverse using [Idle Callbacks](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback)</div>
- ### <div class="mb-4">The browser provides a time window to act</div>
- ### <div class="mb-4">The parser <span class="text-red">pauses and resumes</span> as needed</div>
- ### <div class="mb-4">The parser <span class="text-red">accepts</span> incomplete DOM trees</div>

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
image: ./assets/images2/bitmap.jpeg
---

# Draw the bitmap
<br />

<v-clicks>

- ### <div class="mb-4">Transform the parsed DOM into a <span class="text-red">bi-dimensional array</span></div>
- ### <div class="mb-4">The bitmap has the same size of the viewport</div>
- ### <div class="mb-4">Pixels are <span class="text-red">color-coded</span></div>
- ### <div class="mb-4">The closest-to-the-user elements are drawn on top</div>
- ### <div class="mb-4">A component's weight affects the <span class="text-red">border thickness</span></div>

</v-clicks>

<!--
Regarding the bitmap:
1. We generate a bi-dimensional array that represents the page, with the same screen width and height
2. We set different "colors" for the "pixels". This is necessary to mimic (even if it's not perfect) the CSS depth logics and count the closest-to-the-user elements
3. Then we count the pixels
-->

---
layout: image-right
image: ./assets/images2/bitmap2.jpeg
---

# Bitmap Optimization
<br />

<v-clicks>

- ### <div class="mb-4">We got help from an expert: <span class="text-red">Massimiliano Mantione</span></div>
- ### <div class="mb-4">Transform the array to be <span class="text-red">mono-dimensional</span></div>
- ### <div class="mb-4">Switch to <span class="text-red">Typed Arrays</span></div>
- ### <div class="mb-4">Make the code branch-free, removing most conditional statements</div>
- ### <div class="mb-4">Run the bitmap drawing in a <span class="text-red">[Web Worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)</span></div>

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
layout: default
---

<v-clicks>

- ### <div class="mt-10 mb-10">❌ The initial implementation took `5 blocking seconds` </div>
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
image: ./assets/images2/happy-scientist.jpeg
---

# Yes!  
<br />

<v-clicks>

- ### <div class="mb-10">It runs in production</div>
- ### <div class="mb-10">It gives real <span class="text-red">time data</span></div>
- ### <div class="mb-10">It provides great <span class="text-red">insights</span> for the Leadership</div>

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
- ### <div class="mb-2">It's <span class="text-red">configurable</span></div>
  - ### <div class="mb-2">You are responsible to identify the DS components</div>
  - ### <div class="mb-4">You are responsible to set the components' weight</div>
- ### <div class="mb-4">You can split the page into different containers</div>
- ### <div class="mb-4">It's <span class="text-green">Open Source</span></div>

</v-clicks>

---
layout: default
---

# Things to consider
<br />

<v-clicks>

- ### <div class="mb-4">Collecting data in production comes with <span class="text-red">some cost</span></div>
- ### <div class="mb-4">The coverage data change over-time <span class="text-yellow">*(thinks of the stock market)*</span></div>
- ### <div class="mb-4">It complements static analysis</div>
- ### <div class="mb-2">It's a <span class="text-red">monitoring</span> metric</div>
  - ### <div class="mb-4">You can check the trends only after publishing a page</div>

</v-clicks>

---
layout: default
---

# The progress so far
<br />

<v-clicks>

- ### <div class="mb-4">✅ Preply battle tested in production (1+ year)</div>
- ### <div class="mb-2">✅ Detailed articles</div>
  - ### <div class="mb-2">[Visual coverage part 1](https://shorturl.at/FmcXr)</div>
  - ### <div class="mb-2">[Visual coverage part 2](https://shorturl.at/7Pj5Z)</div>
  - ### <div class="mb-2">For more articles go to [medium.com/preply-engineering](https://medium.com/preply-engineering)</div>
- ### <div class="mb-4">✅ Open Source the project</div>
- ### <div class="mb-4">🚧 Implementing a devtool</div>
- ### <div class="mb-4">🚧 Scaling it at WorkWave</div>
- ### <div class="mb-4">🚧 Helping <span class="text-red">[docplanner.com](https://www.docplanner.com/)</span> and <span class="text-red">[monday.com](https://monday.com/)</span> to adopt it</div>

</v-clicks>

---
layout: default
---

# What about React Native? 
<br />

<v-clicks>

- ### <div class="mb-4">It doesn't offer the same convenient <span class="text-red">worker APIs</span></div>
- ### <div class="mb-4">It doesn't offer a way to query the DOM yet</div>
- ### <div class="mb-4">For now, we run the coverage in <span class="text-red">E2E tests</span></div>
- ### <div class="mb-8">A small <span class="text-red">Swift</span> script extract the available view coordinates</div>
- ### <div class="mb-2">In the future</div>
  - ### <div class="mb-2">`worklets`</div>
  - ### <div class="mb-2">`react-strict-dom`</div>
  - ### <div class="mb-2">Could simplify the process</div>

</v-clicks>


---
layout: statement
---

## [<span class="text-gray">github.com/preply/</span><span class="text-red">design-system-visual-coverage</span>](https://github.com/preply/design-system-visual-coverage)
<br />

## <span class="text-red">Thank you!</span>
<br />

<div style="display: flex; justify-content: center; align-items: center; flex-direction: column; gap: 1rem;">
  <img src="./assets/qrcode.png" width="25%" />
</div>

[grusp.org/<span class="text-red">agenda</span>](https://grusp.org/agenda)

[<span class="text-red">preply</span>.com/en/careers](https://preply.com/en/careers) <span style="display: inline-flex; width: 50%;"></span> [careers.<span class="text-red">workwave</span>.com](https://careers.workwave.com/)
