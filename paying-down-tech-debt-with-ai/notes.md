## Goal
I want to motivate conference goers to look for opportunities to use AI to pay down tech debt.

## Throughline
You just got two promotions — no raise, no title change, but the job description moved up a level.
Everything in this talk supports that claim.

## Ideas
- I like the term "buzzword compliant"
- A matrix with 4 quadrants
  - If it is slow and low benefit, make a Jira ticket and never do it. 
  - If it's fast and high benefit, call an incident. (If it is late in the business day, call the incident tomorrow morning)

## Outline
- Thesis: You just got two promotions
- The trade-off: AI made some debt cheap to pay and some debt cheaper to accrue
  - The good news: some debt is now trivially cheap to pay
  - The bad news: the power dynamic is shifting
  - Tech debt as a service: LLM coding assistants generate tech debt for you way faster than you ever could — a jab at the tools, not the people using them.
  - The bubble talk is about subscriptions. The inference business is profitable — that's the rate your employer pays — so it doesn't go away, and the cost per unit of intelligence only trends down.
  - The only way forward is to get faster at paying it down.
  - Why AI software development is not going away — we can't wait for the stock market bubble to pop for the debt accrual to slow down.
- The real value: knowing where to go slow
  - Ally or Dr. No: willing to move fast on cheap debt so you can spend capital on the hard stuff
- The rename: stop calling it debt — call it a liability, high-interest debt, or a drag on productivity
  - The word "debt" works against you with business leaders; the new words only work if you're selective with them.
  - Software ages like milk, not wine: on-time dependency updates are maintenance, late updates stack breaking changes and lock you out of security fixes.
  - Some things that used to be an asset have become a liability: a customer-facing feature users already rely on. AI makes shipping features faster, so the pile of "we shipped it, now we're stuck with it" grows faster too. It's the only debt where paying it down has a visible cost to users, not just to engineers — removing it is a product decision wearing an engineer's hat.
- The closing thesis
- How I have used it to pay down tech debt.
  - Terraform
  - Scripts to edit DataDog resources
  - Cyclic Dependencies
  - Test flakes
  - Jason -> JSON
  - ALL the CI checks & local pre-commit hooks, in shared repos.

## Exact words
- Political Capital
Every engineer in this room has a mental backlog of tech debt that they know exactly how to fix. And every engineer in this room has been told the exact same thing. Not now, let's first get XYZ feature out the door. Tech debt remaining unpaid long after it's identified, has never been a technical problem, it's a political one. 

## Thesis: You just got two promotions

### The trade-off: AI made some debt cheap to pay and some debt cheaper to accrue
Some types of tech debt are so easy to define for an AI agent that you can hand them off in seconds, with no political capital required:
- "Cover this functionality with tests" — unit, integration, high-level, whatever fits.
- "Check for outdated dependencies and update them."
- "Here's a flaky test — make it less flaky."

These work because each is a closed loop: the agent can verify its own work. Tests pass, dependencies resolve, flakes stop failing. The cost of paying this debt collapsed from a sprint of negotiation to an afternoon and a prompt.

Five years ago, turning a product specification into working code was a scarce, high-value skill — and that scarcity was your leverage. Today that ability is being commoditized. Productivity per engineer is up, teams ship more with fewer people, and product managers and designers are starting to open PRs themselves. The job market for software engineers is at an all-time low. None of this means the engineer is gone — it means the automatic political clout that used to come with the role is gone. The power dynamic shifted, and the old leverage no longer holds on its own.

There's a darker flip side to the same tools: **tech debt as a service**. LLM coding assistants and agents will generate tech debt for you way, way faster than you ever could on your own. It's a jab at the tools, not at the people using them — but it's true, and the room will feel it.

The bubble talk is about subscriptions. The inference business is profitable — that's the rate your employer pays — so it doesn't go away, and the cost per unit of intelligence only trends down.

The only way forward is to get faster at paying it down. And AI software development is not going away — we can't wait for the stock market bubble to pop in order for the debt accrual to slow down.

I used to think the AI stock bubble meant coding assistants would get expensive and scarce. Then I realized my employer already pays API billing rates for our coding assistants, and the large AI companies make real profit selling inference at those rates. The flat subscriptions like SuperGrok are the subsidized side. So even if a lab like OpenAI went bankrupt and sold its assets, somebody would keep selling inference, because it's profitable. The price per token has been trending down for years and will keep trending down. That means heavy AI-assisted coding at work is never going to slow down — it's not a bubble we can wait out.

### The real value: knowing where to go slow
The scarce skill is no longer turning ideas into code — that got cheap. What stayed expensive is knowing which ideas are worth having, and convincing someone to fund them. In 2026, the engineer's real value is understanding where we need to go slow: the technical platform that has to exist before a PM or designer can safely ship PRs.

Things like the database schema, the CI pipeline, the deploy process, the software development lifecycle — a PM or designer will never know to ask about these. Hand Claude Code a proposed database schema and they'll say yes to the first thing they see; if it works, they ship it. The engineer is the person who sees the cliff before the car goes over it.

Some of these decisions are irreversible:
- No code formatting, linting, or quality checks at two hundred fifty thousand lines of code — introducing them then is a massive problem.
- No tests at two hundred fifty thousand lines — writing them after the fact is unsustainable.
- Poor code quality that becomes more and more difficult to maintain as the codebase grows.

This isn't just "don't incur debt." It's triage. Some debt is cheap to pay later — a messy folder structure, a slightly awkward API. Some debt is permanent. The skill is knowing which is which, and that's exactly what you sell to the business: not "let me fix things," but "here's what breaks if we don't decide now."

The emerging thought I'm wrestling with: a good software engineer can triage the implementation itself. Which parts can just be vibe coded. Which parts need very careful thought. And which parts require the business to answer questions before anyone writes a line. That triage — not the typing — is the value.

The thought I'm landing on: you need to become very good at realizing which types of tech debt will still be difficult to pay down even with smarter AI a year or two from now, and which types are cheap to pay down even today with today's AI. Say yes to moving fast and not caring about the cheap types. Pump the brakes and spend your political capital when you see the hard types — the ones that will be painful to fix later no matter how good the AI gets.

Do they see you as an ally, or do they see you as Dr. No? In the age of AI coding, you have to be willing to move fast and overlook some cheap tech debt — otherwise you become the person who always says no. That credibility is what lets you tell people to slow down and review the database schema together before moving forward. Ally on the cheap stuff, Dr. No on the irreversible stuff.

### The rename: stop calling it debt
The word "debt" works against you with business leaders. Consumer debt is always bad; business debt against an asset is leverage they believe they can outgrow. So "we have tech debt" lands as "we're being responsible," not "we're in trouble" — they hear minimum payments as fine. The move: stop calling it debt. Call it a liability, high-interest debt, or a drag on productivity — language the business already treats as a problem. Even if the industry keeps saying tech debt, for how we think and talk about it, use the words that make them feel the compounding cost.

That responsibility cuts both ways: you cannot overstate the problem. Not everything lumped under tech debt today is a liability. Some of it you just hand to an agent at the start or end of the day and you're done. The rename only works if you're selective with it — call the cheap stuff cheap and the expensive stuff expensive, or the business stops believing either label.

Software ages like milk, not wine. A lot of dependencies are an asset doing work you didn't have to write by hand — updating them on time, staying no more than a few months behind, is just making your payments on time, and "debt" isn't even the right word there. It's an asset that needs maintenance. But fall six months or a year behind on a language runtime, a compiler, or your packages, and you stack breaking changes, land in version combinations the rest of the industry has never tested, and a newly found vulnerability can leave you unable to patch at all because the fix lives three major versions ahead. With money, skipping a payment just costs you more later; with software, skipping an update can lock the door.

Some things that used to be an asset have become a liability. A customer-facing feature users already rely on — if you decide you no longer want to maintain it, taking it away gets you bad reviews. AI makes shipping features faster than ever, so the pile of "we shipped it, now we're stuck with it" grows faster too. It's the only kind of debt where paying it down has a visible cost to users, not just to engineers. Removing it is a product decision wearing an engineer's hat.

### The closing thesis
The same AI that ate your leverage is the tool that pays the debt. You don't need political capital anymore because the cost collapsed — but you do need sharper people skills, because your ability to turn an idea into instructions for a computer is no longer the phenomenally valuable skill it was five years ago. Your understanding of what humans want from the software, and your ability to convince a business leader that some time must be taken out for tech debt, is where the value lives now. Engineers who can see the debt and sell the fix are the ones who keep their seats.
