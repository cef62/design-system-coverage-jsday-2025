---
theme: seriph
background: https://cover.sli.dev
title: Design System Visual Coverage
class: text-center
drawings:
  persist: false
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
transition: slide-left
---

# Design System Visual Coverage

A story of how we measure the impact of our design systems in production!

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/xxxxx" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

---
layout: image-right
image: ./assets/pixels.png
---

# "Paint" over the DOM!

- We color DOM elements
- Battle tested in production
- Open source 
- 100% plain JS

---
layout: center
---

# Wait a moment...

---
layout: center
class: text-center
---

# Coloring DOM elements ain't nothing new!


---
layout: center
class: text-center
---

# But...
# ...doing it on users' devices on a high-traffic website is something no one did!


---
layout: center
class: text-center
---

# We transform 
# pixels into bitmaps 
# and bitmaps into coverage metrics
<div style="display:flex; gap:8px;">
  <img width="200" src="./assets/pixels.png" />
  <img width="200" src="./assets/bitmap.png" />
  <img width="200" src="./assets/metrics.png" />
</div>


---
layout: center
---

# Who are we?

---

# Stefano Magni @ Preply

- XXXX
- XXXX
- XXXX


---

# Matteo Ronchi @ WorkWave

- XXXX
- XXXX
- XXXX

---
layout: center
class: text-center
---

# Why are we doing this?

---
layout: image-right
image: https://cover.sli.dev
---

- Our products are very data-oriented
- Platform teams must create long-term strategy and track progress through quarterly OKRs
- Metrics must be approved by the Leadership Team


---
layout: center
class: text-center
---

# What data do DS teams usually use?

---
layout: center
class: text-center
---

# Static Analysis 
## How many times is a component used?

---
layout: image-left
image: https://cover.sli.dev
---

Static analysis doesn't help us understand the impact on what users see!


- 1000 button instances doesn't translate to 1000 buttons seen by the users
  - Dead code
  - Not all the pages are equally important
- Data is collected per codebase, not per page/feature

---
layout: center
class: text-center
---

# Visual Coverage
## How the DS impact the users?

---
layout: center
---

- Different pages have different importance
- Data is collected per page and per Product
- Data can be grouped by team
- Metrics that matter for your leadership

<img width="100%" src="./assets/dashboard.png" />

---
layout: center
class: text-center
---

# A component's weight

---
layout: center
---

- A component's weight is subjective to your Product
- Smaller elements might weight more

<img width="100%" src="./assets/pixels.png" />

---
layout: cover
background: https://cover.sli.dev
---

## Finetune your components weight

---
layout: statement
class: text-center
---

# When you calculate the coverage?

---
layout: image-right
image: https://cover.sli.dev
---

- E2E tests?
- Story tests?
- Coverage is limited
- Adopting the coverage could affect the teams' velocity

---
layout: two-cols-header
---

# What about adding it straight to production?

::left::

- Calculating the coverage won't affect your teams
- The DS team can operate independently
- We have big numbers

::right::

- It must be done without impacting the UX
- It requires careful performance optimizations
- Preply already runs it in production

---
layout: center
class: text-center
---

# Preply vs WorkWave use cases

---
layout: center
class: text-center
---

# What do they have in common? 
## Nothing, but the DS coverage works for both!

---
layout: two-cols
---

# Preply

- B2C
- Millions of users
- A single Product
- Many "connected" teams
- Pages owned by multiple teams
- Pages known in advance (by the DS team)
- Full control over the DS components 


::right::

# WorkWave

- B2B
- Thousands of clients
- Multiple independent Products
- Many not "connected" teams
- Pages owned by a single team
- Pages not known in advance (by the DS team)
- Partial control over the DS components

---
layout: center
class: text-center
---

# It's not perfect...

---
layout: center
---


<img width="100%" src="./assets/page-popularity.jpeg" />

- Collecting events in Production comes with a cost
- The collected data is not stable (Thinks about the stock market)
- It's a monitoring metric 
  - It's hard to say "by implementing this component, we expect an increase of X %"
- It complements static analysis, is not a replacement
- It greatly helps you understand the impact of your DS

# ...but it works!

---
layout: image-right
image: https://cover.sli.dev
---

# React Native

- No JS multi-threading
- Luckily, Preply has a lot of E2E tests
- [Worklets](https://developer.mozilla.org/en-US/docs/Web/API/Worklet) FTW


---
layout: image-right
image: https://cover.sli.dev
---

# Progress so far

- ✅ Battle tested in production at Preply
- ✅ Detailed articles 
- ✅ Open Source
- 🚧 Implementing a devtool
- 🚧 Scaling it at WorkWave

---
layout: end
---

# Thank You!