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
## Lessons from Helping software dev teams adopt AI
### Chris Nelson
@superchris.launchscout.com (BlueSky)
github.com/superchris
![h:200](/images/full-color.png#title-slide-logo)

---

# Agenda
- Where are we and how did we get here?
- What works **today**?
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

---
# You might be seeing this:
> it’s like magic ✨ I ask it to redesign a website or to write unit tests, and it just churns through it like it’s nothing. 
> Things that would’ve taken me lots of time, and more importantly, _energy_, are finished in no time at all. 10x engineer status is within my grasp.

---
# Or this:
> Claude deletes my test file instead of adding a new test. 
> It tries to make a change, realizes it failed, tries again, realizes it failed again. 
> It edits unrelated files, adding non-sensical comments. It’s suddenly unable to generate code that compiles. 
> The auto-completes try to delete every line of code I look at, even after I keep dismissing it.

---

# Fun fact:
## These are from the same person!

---

# You also might be seeing this...

---

# Junior devs
- Can make more progress than ever before
- Less memorization of obscure technical details
- Often enthusiastic AI adopters

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

# So why the split?

---

# Junior devs
- In some cases, may not know what they don't know
- May not yet understand the *why* behind best practices

---

# Senior devs: Let's talk about the quiet part out loud
- We've been rooting for AI to fail
- It's scary!
- It looks like everything we love about our career is ending
  - No one will care about good code
  - No one will care about good practices

---

# So what happened to bring me around?

---

# The basic problem: Generating code isn't enough
## Nobody is perfect!
- LLMs hallucinate
- Humans just make mistakes :)

---

# This leaves us with two options
- Looks like it works: Ship it! (Vibe coding)
  - starts off ok
  - things go off the rails pretty quick
- Carefully review everything
  - And hope you don't miss anything!
  - Blech!

---

# How do humans get better at writing code?

---

# Improving the feedback loop
- We need to know if our code works!
- Running it and looking at results is slow and tedious
- What if we could automate that?

---

# TDD: Test Driven Development
- Writing code that tests our code
  - Gives a simple pass/fail result
  - Unit tests test portions of an app
  - End to end tests test the whole thing
  - We need both
- <span style="color: #e74c3c;">**Red**</span>, <span style="color: #27ae60;">**Green**</span>, <span style="color: #6042BC;">**Refactor**</span>
  - Start with a <span style="color: #e74c3c;">**failing test**</span>
  - <span style="color: #27ae60;">**Make it pass**</span>
  - <span style="color: #6042BC;">**Clean up the code**</span>

---

# The Skynet moment
- 2024 - Cursor adds "Composer mode"
  - before tools could generate code
  - now it can run commands and see their output
- Before it could write tests, **now it can run them**
- *AND* see the results
- *AND* react to the results to **fix its' own mistakes**
- This **dramatically** improved the usefulness of AI tooling

---

# And now it's safer to clean things up
- AI has gotten pretty good and generating code that works
- This isn't always *good* code
- It *is* often able to improve it's own code
- And with tests, we can do it without breaking things

---

# So this got us to "net positive"
## But there were still some bumps in the road...

---

# Accepting non-determinism
- It's going to be great some days, and terrible others
- This makes it hard to decide if it's worth it

---

# Solution: Measure the averages!
- Try it on a real(istic) project
- Even 1-2 weeks is enough
- Accounts for good days and bad days
- Need to have some idea of initial average velocity

---

# Example: 2 week spreadsheet replacement project
- Real project with a client
- Defined time box: 2 weeks, 80 hours
- Team: 1 developer (Chris) + 0.5 designer (Katie)
- Results:
  - Plenty of crazy adventures!
  - 40 cards completed
  - Normal velocity: 4-5 cards per week
  - ***4x improvement***

---

# Remembering to reach for it
### It can feel like an interruption to flow

---

# Stuff to try
- Pair (or mob) with someone
  - See some wins
- Try it on things you hate doing :)

---

# Keeping your brain engaged
- It can write code faster than you can read it
- This is the one I struggle with the most
- More of an issue with languages I use less

---

# What helped:
- Tests are a great line of defense
  - chances of hallucinating both the test and code in offsetting ways are smaller
- Ask the AI to explain things you don't understand
  - LLMs are often better at explaining code than writing it
- Be critical!
  - It will often write code that is "suboptimal"
  - Tell it to do better!

---

# Giving up too quickly
## It will often fail before it succeeds

---

# Things to try
- Tests often can give it the feedback it needs to get it right
- Saying it again a different way
- Breaking the problem down smaller

---

# Giving up too slowly
## Learning when it's time to take the wheel
- Failing three times is a good rule of thumb
- You might see patterns in what it fails at

---

# LLM tarpits
## If it's confusing you, its' confusing the LLM...
- Some parts of any tech stack are just not intuitive
- Some tech stacks are more intuitive than others
- Documentation can help
- Examples are even better

---

# Example: Nested association froms in LiveView
- They work well, but aren't intuitive
- LLMs would make a mess of them *predictably*
- Solution: do one myself, use it as an example

---

# Moving the bottleneck
- You can deliver features faster, yay!
- But they still need to be:
  - Accepted
  - Deployed
  - Documented
  - Marketed
- **You likely need to plan for more Product Owner availability**

---

# Example: 2 week experiment
- The CEO was the "product owner"
- He only had so much time to give us
  - Sometimes we had to guess
  - We kinda got away with it ;)

---

# Things we've learned..

---

# If you specify, you don't have to guess...

---

# Getting specific
- OpenAPI spec
- Typed interfaces
- UI DSLs or Component Library
- AI can help generate all of these

---
# Example: adding OpenAPI to a Microservices project
## Before
- AI made decent guesses from existing example
- But guessed differently for front and back end
## After
- AI generated an OpenAPI spec
- code generators generate typed stubs
- AI fills in the blanks
- **much higher successs rate**

---

# Don't sleep on old skool code generators!
- Yes, LLMs can generate code
**BUT**
- Code generators can generate code
  - ***The same way every time***
- And LLMs can run code generators

---

# A picture is worth 1000 ~~words~~ tokens
- AI is astonishly good implementing a UI from mocks
- Seems to work regardless of specific tech
  - HTML/CSS, React, Rails, Elixir/Phoenix
- Could be a Figma mock, or a picture of a napkin
- Pretty good at fixing what it doesn't get quite right

---

## Don't bring a ~~knife~~ non-deterministic code generator to a ~~gun fight~~ problem easily solvable with deterministic code
- If it's scriptable, ask it to write a script
  - Converting between file formats
  - Search and replace

---

# Example: Understanding Oracle Form export
- Oracle Form exports as XML
  - Embedded code within the XML
- Ask cursor to explain/convert each file
- *OR* Ask cursor to write an script to extract metadata and code to separate files

---

# Give it a smaller sandbox to play in
## So it can make less of a mess :)

---

# DSL example from Tim

---

# Give AI the ability to ask questions
- Without enough detail, AI makes educated guesses
- Educated guesses = hallucinations
- Give it tools to ask for exactly what it needs

---

# Model Context Protocol (MCP)
- New standard for connecting AI assistants to data sources
- Gives LLMs the ability to "reach out" to external environment
- Examples:
  - Query your database
  - Read your logs
  - Access your APIs and documentation

---

# How to MCP
- Make sure your code assistant supports it
- Make sure your other tools support it
  - They likely do or plan to already
  - Building custom MCP tools is pretty easy

---

# Example: Oracle forms conversion
- It could figure out a lot from source
- But not table schemas
- So it would make them up
- We added an "execute_query" tool
  - No more guessing!

---

# Adding documentation
- AI can read and follow docs
  - not perfectly but enough that it's worth doing
  - good for environment specific or less common things
- AI can also help write docs
  - but you should carefully review what it comes up with
- Process docs are also helpful
  - but again, it won't follow them perfectly

---

# Example: Describing TDD
- Added a cursor rule
- Pretty good success
- Often needs reminding to follow it

---

# How we help teams make the leap

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

# Thoughts and predictions

---

# Language matters
- LLMs do better with intuitive languages
  - Ruby, Elixir
- Can struggle with "difficult" languages
  - Rust
  - but getting better

---

# Languages and Tech stacks embracing LLMs
- TideWave
  - MCP server integrated with Rails and Phoenix
- LLM friendly usage rules
- Generating prompts

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

# Projects that benefit the most
- Legacy rewrites
- Anything with repeated similar things

---

# Revisiting Buy vs Build

---

# Questions

![h:500](/images/qrcode.png)
---
