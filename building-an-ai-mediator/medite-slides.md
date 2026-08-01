---
marp: true
author: De Wet Blomerus
size: 16:9
theme: default
---

<style>
  :root {
    --color-fg-default: #FFFFFF;
    --color-canvas-default: #252B31;
    font-size: 50px;
  }

  h1, h2, h3 {
    font-weight: 400;
    color: white;
  }

  h1 {
    font-size: 100px;
  }

  h2 {
    font-size: 80px;
  }

  h3 {
    font-size: 60px;
  }

  section {
    background-image: url(atldevcon-logo-white.png);
    background-repeat: no-repeat;
    background-position: bottom 20px right 20px;
    background-size: 200px auto;
  }
</style>

# Building an Ai mediator

---

![bg cover](sponsors.jpg)

---

# Who am I?

- I am not an AI expert.
- I am an expert at building things.

---

# What did I build?

- Problem discovery story.
- Demo.
- Where I paused the project.

---

### What did I learn about building generative text applications?

- Use an API.
- Send the entire context in each request.
- Send a system prompt.
- Plan to swap out your vendor.

---

### What have I learned about building software.

- Build stuff with other people. (obviously)
- Build stuff by yourself.

---

### Choosing a stack of tools to build with

You have three large pieces to choose

1.  Present to user (web, mobile, desktop, hardware)
1.  Logic (programming language or no/low-code platform)
1.  Data Store (Database). Maybe collapse with previous bullet into a BaaS like Firebase or Supabase

---

### Choosing a stack (continued)

You have many small pieces to choose.

- Distribution, hosting. PaaS is really compelling for side projects. I like Fly.io
- Authentication/Authorization. Maybe separate bullets, maybe BaaS from previous slide.

---

### Choosing a stack (continued some more)

- Am I motivated to learn it?
- Do I enjoy working with it?
- Can I get paid doing it?
- Do I have or can I find a community?

---

### My stack

- I chose Phoenix LiveView for side projects.
- Then I found a job doing it.

---

### Now what?

- Go build a side project
- After you build one, cranking out one per year becomes less and less work.

https://github.com/dewetblomerus/mediate-talk/blob/main/slides.pdf
