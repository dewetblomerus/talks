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
    color: black;
  }

  a {
    color: black;
    font-weight: 200;
  }

  h1 {
    text-align: center;
    font-size: 60px;
  }

  h2 {
    font-size: 40px;
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
    right: 40px;
    bottom: 30px;
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
    height: 200px;
    display: block;
  }

  /* Second slide: image only — hide the footer logo. */
  section.full-image footer {
    display: none;
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
- All debt is master to accrue

