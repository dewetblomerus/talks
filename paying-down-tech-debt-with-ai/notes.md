## Goal
I want to motivate conference goers to look for opportunities to use AI to pay down tech debt.

## Ideas
- All the regular risk/reward structures apply.
  - Debt can be paid off too aggressively.
  - Money-making activities can be approached too aggressively.
  - Is it debt, or is it just bills? Are you in debt, or are your fixed costs just too high? Either could have you - living paycheck to paycheck.
  - Do you have debt, or do you have lifestyle creep?
  - Software ages like milk, not like wine.
  - In tech, when does an unpaid bill become debt?
  - I like the term "buzzword compliant"
  - Ukelele factor
  - Or do they see you as doctor No.
  - Tech debt as a service 
  - There is nothing as permanent as a temporary fix
  - Poor code quality, more and more difficult to maintain. 
  - Something that used to be an asset, that has become a liability. 
  - Assets that are difficult to remove. Like P2P
  - A matrix with 4 quadrants
    - If it is slow and low benefit, make a Jira ticket and never do it. 
    - If it's fast and high benefit, call an incident. (If it is late in the business day, call the incident tomorrow morning)

## Outline
- Political Capital
  - Thesis: The leverage moved from your hands to your head
    - The good news: some debt is now trivially cheap to pay
    - The bad news: the power dynamic is shifting
    - The real value: knowing where to go slow
    - The closing thesis
- What AI software development means for tech debt.
  - We are building faster, so we are accruing debt faster.
- Why AI software development is not going away.
  - This means we can't wait for the stock market bubble to pop in order for the debt accrual to slow down.
- How I have used it to pay down tech debt.
  - Terraform
  - Scripts to edit DataDog resources
  - Cyclic Dependencies
  - Test flakes
  - Jason -> JSON

## Exact words
- Political Capital
Every engineer in this room has a mental backlog of tech debt that they know exactly how to fix. And every engineer in this room has been told the exact same thing. Not now, let's first get XYZ feature out the door. Tech debt remaining unpaid long after it's identified, has never been a technical problem, it's a political one. 

## Thesis: The leverage moved from your hands to your head

### The good news: some debt is now trivially cheap to pay
Some types of tech debt are so easy to define for an AI agent that you can hand them off in seconds, with no political capital required:
- "Cover this functionality with tests" — unit, integration, high-level, whatever fits.
- "Check for outdated dependencies and update them."
- "Here's a flaky test — make it less flaky."

These work because each is a closed loop: the agent can verify its own work. Tests pass, dependencies resolve, flakes stop failing. The cost of paying this debt collapsed from a sprint of negotiation to an afternoon and a prompt.

### The bad news: the power dynamic is shifting
Five years ago, turning a product specification into working code was a scarce, high-value skill — and that scarcity was your leverage. Today that ability is being commoditized. Productivity per engineer is up, teams ship more with fewer people, and product managers and designers are starting to open PRs themselves. The job market for software engineers is at an all-time low. None of this means the engineer is gone — it means the automatic political clout that used to come with the role is gone. The power dynamic shifted, and the old leverage no longer holds on its own.

### The real value: knowing where to go slow
The scarce skill is no longer turning ideas into code — that got cheap. What stayed expensive is knowing which ideas are worth having, and convincing someone to fund them. In 2026, the engineer's real value is understanding where we need to go slow: the technical platform that has to exist before a PM or designer can safely ship PRs.

Things like the database schema, the CI pipeline, the deploy process, the software development lifecycle — a PM or designer will never know to ask about these. Hand Claude Code a proposed database schema and they'll say yes to the first thing they see; if it works, they ship it. The engineer is the person who sees the cliff before the car goes over it.

Some of these decisions are irreversible:
- No code formatting, linting, or quality checks at two hundred fifty thousand lines of code — introducing them then is a massive problem.
- No tests at two hundred fifty thousand lines — writing them after the fact is unsustainable.

This isn't just "don't incur debt." It's triage. Some debt is cheap to pay later — a messy folder structure, a slightly awkward API. Some debt is permanent. The skill is knowing which is which, and that's exactly what you sell to the business: not "let me fix things," but "here's what breaks if we don't decide now."

The emerging thought I'm wrestling with: a good software engineer can triage the implementation itself. Which parts can just be vibe coded. Which parts need very careful thought. And which parts require the business to answer questions before anyone writes a line. That triage — not the typing — is the value.

### The closing thesis
The same AI that ate your leverage is the tool that pays the debt. You don't need political capital anymore because the cost collapsed — but you do need sharper people skills, because your ability to turn an idea into instructions for a computer is no longer the phenomenally valuable skill it was five years ago. Your understanding of what humans want from the software, and your ability to convince a business leader that some time must be taken out for tech debt, is where the value lives now. Engineers who can see the debt and sell the fix are the ones who keep their seats.
