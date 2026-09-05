---
marp: true
author: De Wet Blomerus
size: 16:9
theme: default
footer: '![logo](images/backgrounds/logo.png)'
---

<style>
  :root {
    color: black;
    background: white;
  }

  h1, h2, h3 {
    font-weight: 300;
    text-align: center;
    color: black;
  }

  a {
    color: black;
    font-weight: 200;
  }

  /* Marp default body is ~35px. Sparse slides: bump the slide root. */
  section {
    font-size: 42px;
  }

  h1 {
    font-size: 72px;
  }

  h2 {
    font-size: 56px;
  }

  pre, code {
    background-color: white;
    color: black;
  }

  /* Logo on every slide, via the footer directive. It must be a real
     element: Marpit forces background:transparent!important and hides
     ::before/::after on any slide that uses ![bg]. */
  footer {
    position: absolute;
    left: auto;
    right: 18px;
    bottom: 18px;
    margin: 0;
    padding: 0;
  }

  /* Full-bleed foreground image: sits above the slide background,
     below the footer logo. */
  section.full-image {
    padding: 0;
  }

  section.full-image > p {
    margin: 0;
  }

  section.full-image > p > img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  footer img {
    height: 160px;
    display: block;
  }

  /* Second slide: image only — hide the footer logo. */
  section.full-image footer {
    display: none;
  }

  /* 2x2 triage matrix. Leave room for the footer logo. */
  section.matrix {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-right: 200px;
    padding-bottom: 40px;
  }

  section.matrix table,
  section.matrix thead,
  section.matrix tbody,
  section.matrix tr,
  section.matrix th,
  section.matrix td {
    border: none !important;
    background: transparent !important;
    font-weight: 300;
  }

  section.matrix table {
    width: 100%;
    table-layout: fixed;
    border-collapse: collapse;
    margin: 0;
  }

  section.matrix thead th:first-child,
  section.matrix tbody td:first-child {
    width: 140px;
  }

  section.matrix thead th {
    text-transform: uppercase;
    letter-spacing: 0.14em;
    font-size: 28px;
    padding: 0 12px 10px;
    height: auto;
  }

  section.matrix tbody td:first-child {
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-size: 24px;
    padding: 0 16px 0 0;
    line-height: 1.2;
    text-align: center;
    vertical-align: middle;
  }

  section.matrix tbody td:not(:first-child) {
    border: 2px solid currentColor !important;
    text-align: center;
    vertical-align: middle;
    font-size: 36px;
    line-height: 1.25;
    padding: 16px 20px;
    height: 230px;
  }

</style>

![bg](images/backgrounds/light-background.png)

# Paying Down Tech Debt With AI

---

<!-- _class: full-image -->

![Vasa](images/vasa.avif)

---

![bg](images/backgrounds/light-background.png)

# The Tradeoff
- Some debt is much faster to pay off
- All debt is faster to accrue

---

![bg](images/backgrounds/light-background.png)

# Aren't We Just In A Bubble?

---

<!-- _class: matrix -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Spend political capital | Call an incident |
| Low benefit | Jira | Hand it to an agent |

---

![bg](images/backgrounds/light-background.png)

# The real value: knowing where to go slow
  - Ally or Dr. No: willing to move fast on cheap debt so you can spend capital on the hard stuff


---

![bg](images/backgrounds/light-background.png)

# Hard to pay later: architecture
  - A good system design
  - A good database schema
  - A consistent API contract

---

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

![bg](images/backgrounds/light-background.png)

# Yes to all of the following? Easy!
  - Easy to verify it doesn't break anything
  - Can be deployed as a single change in a single repo
  - The directories containing the code communicates low-risk.

---

![bg](images/backgrounds/light-background.png)

# Debt might be a bad name
