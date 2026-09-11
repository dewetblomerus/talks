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
    padding-top: 20px;
    padding-right: 160px;
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
    width: 170px;
  }

  section.matrix thead th {
    text-transform: uppercase;
    letter-spacing: 0.14em;
    font-size: 38px;
    padding: 0 12px 4px;
    height: auto;
  }

  section.matrix tbody td:first-child {
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-size: 36px;
    padding: 0 4px 0 0;
    line-height: 1.2;
    text-align: center;
    vertical-align: middle;
  }

  section.matrix tbody td:not(:first-child) {
    border: 2px solid currentColor !important;
    text-align: center;
    vertical-align: middle;
    font-size: 48px;
    line-height: 1.25;
    padding: 16px 20px;
    height: 240px;
  }

  /* Progressive bullets: every step slide carries the whole list, so the
     heading and bullets never move. Unrevealed bullets keep their space.
     Use `_class: reveal` for the heading alone, then `reveal reveal-N`
     to show the first N bullets. */
  section.reveal li {
    visibility: hidden;
  }

  /* Matrix cells reveal in a custom order: Jira, Call an incident,
     Hand it to an agent, Tough conversations. The grid and its labels
     stay put; only the cell text is hidden. */
  section.matrix.reveal tbody td:not(:first-child) {
    visibility: hidden;
  }

  section.matrix.reveal-1 tbody tr:nth-child(2) td:nth-child(2),
  section.matrix.reveal-2 tbody tr:nth-child(2) td:nth-child(2),
  section.matrix.reveal-2 tbody tr:nth-child(1) td:nth-child(3),
  section.matrix.reveal-3 tbody tr:nth-child(2) td:nth-child(2),
  section.matrix.reveal-3 tbody tr:nth-child(1) td:nth-child(3),
  section.matrix.reveal-3 tbody tr:nth-child(2) td:nth-child(3) {
    visibility: visible;
  }

  section.reveal-1 li:nth-child(-n + 1),
  section.reveal-2 li:nth-child(-n + 2),
  section.reveal-3 li:nth-child(-n + 3),
  section.reveal-4 li:nth-child(-n + 4),
  section.reveal-5 li:nth-child(-n + 5),
  section.reveal-6 li:nth-child(-n + 6) {
    visibility: visible;
  }

</style>

![bg](images/backgrounds/light-background.png)

# Paying Down Tech Debt With AI

---

<!-- _class: full-image -->

![Vasa](images/vasa.avif)

---

<!-- _class: reveal -->

![bg](images/backgrounds/light-background.png)

# The Tradeoff
- Debt is faster to pay off
- Debt is much faster to accrue

---

<!-- _class: reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

# The Tradeoff
- Debt is faster to pay off
- Debt is much faster to accrue

---

![bg](images/backgrounds/light-background.png)

# The Tradeoff
- Debt is faster to pay off
- Debt is much faster to accrue

---

![bg](images/backgrounds/light-background.png)

# Aren't We Just In A Bubble?

---

![bg](images/backgrounds/light-background.png)

# Software Engineering in 2026
### Knowing when to go slow, while being willing to go fast elsewhere.

---

<!-- _class: matrix reveal -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Tough conversations | Call an incident |
| Low benefit | Jira | Hand it to an agent |

---

<!-- _class: matrix reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Tough conversations | Call an incident |
| Low benefit | Jira | Hand it to an agent |

---

<!-- _class: matrix reveal reveal-2 -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Tough conversations | Call an incident |
| Low benefit | Jira | Hand it to an agent |

---

<!-- _class: matrix reveal reveal-3 -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Tough conversations | Call an incident |
| Low benefit | Jira | Hand it to an agent |

---

<!-- _class: matrix -->

![bg](images/backgrounds/light-background.png)

| | Slow | Fast |
| :--- | :---: | :---: |
| High benefit | Tough conversations | Call an incident |
| Low benefit | Jira | Hand it to an agent |


---

<!-- _class: reveal -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: architecture
  - A good system design
  - A good database schema
  - A consistent API contract

---

<!-- _class: reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: architecture
  - A good system design
  - A good database schema
  - A consistent API contract

---

<!-- _class: reveal reveal-2 -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: architecture
  - A good system design
  - A good database schema
  - A consistent API contract

---

![bg](images/backgrounds/light-background.png)

# Hard to pay later: architecture
  - A good system design
  - A good database schema
  - A consistent API contract

---

<!-- _class: reveal -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

<!-- _class: reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

<!-- _class: reveal reveal-2 -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

<!-- _class: reveal reveal-3 -->

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

![bg](images/backgrounds/light-background.png)

# Hard to pay later: safety nets
  - Observability coverage & consistency
  - Canary deploys
  - Dependabot
  - CI checks: Test coverage, security checks, linting, formatting, large-file checks, duplicate-code checks, etc.

---

<!-- _class: reveal -->

![bg](images/backgrounds/light-background.png)

# Yes to all of the following? Easy!
  - Easy to verify it doesn't break anything
  - Can be deployed as a single change in a single repo
  - The directories containing the code communicates low-risk.

---

<!-- _class: reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

# Yes to all of the following? Easy!
  - Easy to verify it doesn't break anything
  - Can be deployed as a single change in a single repo
  - The directories containing the code communicates low-risk.

---

<!-- _class: reveal reveal-2 -->

![bg](images/backgrounds/light-background.png)

# Yes to all of the following? Easy!
  - Easy to verify it doesn't break anything
  - Can be deployed as a single change in a single repo
  - The directories containing the code communicates low-risk.

---

![bg](images/backgrounds/light-background.png)

# Yes to all of the following? Easy!
  - Easy to verify it doesn't break anything
  - Can be deployed as a single change in a single repo
  - The directories containing the code communicates low-risk.

---

<!-- _class: reveal -->

![bg](images/backgrounds/light-background.png)

# Some things I've done at work to pay down tech debt
  - With the exception of Canary deploys...
  - Reducing cyclic dependencies
  - Fixing flaky tests

---

<!-- _class: reveal reveal-1 -->

![bg](images/backgrounds/light-background.png)

# Some things I've done at work to pay down tech debt
  - With the exception of Canary deploys...
  - Reducing cyclic dependencies
  - Fixing flaky tests

---

<!-- _class: reveal reveal-2 -->

![bg](images/backgrounds/light-background.png)

# Some things I've done at work to pay down tech debt
  - With the exception of Canary deploys...
  - Reducing cyclic dependencies
  - Fixing flaky tests

---

![bg](images/backgrounds/light-background.png)

# Some things I've done at work to pay down tech debt
  - With the exception of Canary deploys...
  - Reducing cyclic dependencies
  - Fixing flaky tests

---

![bg](images/backgrounds/light-background.png)

# Debt might be a bad name
