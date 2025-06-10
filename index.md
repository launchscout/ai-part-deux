---
marp: true
style: |

  section h1 {
    color: #6042BC;
  }

  section code {
    background-color: #e0e0ff;
  }

  footer {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 100px;
  }

  footer img {
    position: absolute;
    width: 120px;
    right: 20px;
    top: 0;

  }
  section #title-slide-logo {
    margin-left: -60px;
  }
---

# Beyond Vibe Coding
## Helping software dev teams effectively adopt AI
### Chris Nelson
@superchris.launchscout.com (BlueSky)
github.com/superchris
![h:200](/images/full-color.png#title-slide-logo)

---

# Agenda
- Where are we now?
- What are the challenges?
- What are the opportunities?
- Where *might* we be headed?
- Questions and discussion

---

# About me
- Very experienced developer
- AI skeptic -> AI adopter
- Recent transition (< 1 year)

---

# What about you?
- Software developers?
- Managers?
- Other?

---

# Where are we now?

---

# We're in a weird place...
## You might be seeing this:
- Junior devs *loving* their AI coding tools
- Senior devs telling you it's all garbage

---

# Junior devs
- Can make more progress than ever before
- Less memorization of obscure technical details
- In some cases, may not know what they don't know
- May not yet understand the *why* behind best practices

---

# But what about senior devs?

---

# My own journey
- I keep hearing about AI coding tools
- I should try ***insert latest tool here***
- Wow it just did something amazing!
- And now it's just generating nonsense
- And now it's taking me more to time to read nonsense than if I wrote the code myself...
- *turns the thing off*

---

# Rinse and repeat
## Until late 2024...

---

# Senior devs: Let's talk about the quiet part out loud
- We've been rooting for AI to fail
- It's scary!
- It looks like everything we love about our career is ending
  - No one will care about good code
  - No one will care about good practices

---

# None of this is true!
- Ok, maybe the scary part is
- AI is not failing
- Everything that makes us good at software development matters even more now!

---

# AI is a force multiplier
- Everything we do it can help us do faster
- We can build great software quickly!
- **OR***
- We can make a giant mess!

---

# Generating code isn't enough
## Nobody is perfect!
- LLMs hallucinate
- Humans just make mistakes :)

---

# How do **we** get better at writing code?

---

# Improving the feedback loop
- We need to know if our code works!
- Running it and looking at results is slow and tedious
- What if we could automate that?

---

# TDD: Test Driven Development
- <span style="color: #e74c3c;">**Red**</span>, <span style="color: #27ae60;">**Green**</span>, <span style="color: #6042BC;">**Refactor**</span>
  - Start with a <span style="color: #e74c3c;">**failing test**</span>
  - <span style="color: #27ae60;">**Make it pass**</span>
  - <span style="color: #6042BC;">**Clean up the code**</span>
- Repeat

---

# What if the computer could do that?

---

# My Skynet moment
- 2024 - Cursor adds "Composer mode"
  - allows it to run commands and see their output
- Before it could write tests, **now it can run them**
- *AND* see the results
- *AND* react to the results to **fix its' own mistakes**

---

# Why does this matter so much?

---

# ~~Hallucinations~~ Mistakes are inevitable
- One of us has to fix them
- Now my AI tool can do it
  - or at least help
- This **dramatically** improved the usefulness of AI tooling

---

# We can avoid compounding a mess
- AI has gotten pretty good and generating code that works
- This isn't always *good* code
- It *is* often able to improve it's own code
- **And now it can do so safely**

---

# Human challenges

---

# Remembering to reach for it

---

# Explaining things well

---

# Keeping your brain engaged

---

# Giving up too quickly

---

# Giving up too slowly

---

# Breaking things down

---

# Machine challenges
## How to guess less

---

# If it's confusing you, its' confusing the LLM...
- Some parts of any tech stack are just not intuitive
- Some tech stacks are more intuitive than others
- Documentation can help
- Examples are even better

---

# Can we specify that?
- OpenAPI spec
- Typed interfaces
- UI DSLs
- AI can help generate all of these

---

# Don't sleep on old skool code generators!
## An approach that worked for us:
- LLM can generate a spec
- Code generators can generate code
  - ***The same way every time***
- LLM can fill in the blanks

---

# Techniques

---

# Document everything
- 

---

# Examples are even better

---

# Step 1: Initial discovery
- What are you trying to do?
- Are there similar things that repeat?
- Where can we eliminate guessing?

---

# Step 2: Research
- We work with AI to build something
- Ideally similar to a "repeating problem"
- We want to find the smooth paths and the rough edges

---

# Step 3: Mob it up!
- Do it again, with an audience
- We drive
- You drive
- Embrace the chaos!
  - Blind alleys and rough edges are good

---

# Tools matter
- We've seen best results with Cursor
  - We hear good things about Aider and Zed
  - This is a *very* dynamic space
- Minimal requirements
  - Edit code
  - Run commands
  - MCP support

---

# Models matter
- Claude has been a consistent winner
- Gemini seems close behind
- Self-hostable models show increasing promise
- Aider leaderboard is worth keeping an eye on

---

# "Old school" deterministic code generators
- scaffolding
- generate from a spec (eg OpenAPI)

---

# Techniques

---

# TDD

---

# More context

---

# Don't make it write all the code

---

# Less guessing

---

# Give AI the ability to ask questions
- Without enough detail, AI makes educated guesses
- Educated guesses = hallucinations
- Give it tools to ask for exactly what it needs:
  - "What's the database schema?"
  - "How does this API work?"
  - "What are the business rules?"
- Result: AI stops guessing and starts knowing

---

# Model Context Protocol (MCP)
- New standard for connecting AI assistants to data sources
- AI can call functions to get real-time information
- Examples:
  - Query your database directly
  - Read your codebase
  - Access your APIs and documentation
- No more copy/pasting context into chat windows!

---

# Documentation helps... to a point

---

# The human experience


---

# A lot of us have been asking the wrong question
## Can it augment us?

---

# Projects that benefit the most
- Legacy rewrites
- Anything with repeated similar things

---

# Revisiting Buy vs Build

---

# Am I there yet?
## What to expect

---

# 
---

# Questions

![h:500](/images/qrcode.png)
---
