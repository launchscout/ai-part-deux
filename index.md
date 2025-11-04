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
## Lessons from Helping software teams adopt AI
### Chris Nelson
@superchris.launchscout.com (BlueSky)
https://launchscout.com/chris-nelson
![h:200](/images/full-color.png#title-slide-logo)

---

# About me
- Co-Founder, Launch Scout
- Very experienced developer
- AI skeptic -> AI adopter
- Recent transition (< 1 year)

---

# Agenda
- Where are we and how did we get here?
- What actually works?
- What are the challenges?
- What are the opportunities?
- Questions and discussion

---

# Disclaimer: This talk is already obsolete
- It's useless to worry that you are behind
- Because everyone else is too :)

---

# What about you?
- What's your experience with using LLMs to write code?
- Positive vs negative
- Size of apps
- What tools?

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

# The basic question: Is Vibe Coding dead?
- Yes!
  - AI does not replace the need to know how to program computers
- But now what?
- Throw everything away and go back?

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
  - agents before anyone used that word
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
- But that doesn't mean it's all smooth sailing
- Let's talk about some challenges

---

# Accepting non-determinism
- It's going to be great some days, and terrible others
- Often success or failure seems not correlated with degree of difficulty
- This makes it hard to decide if it's any good at all

---

# Solution: Measure the averages!
- Try it on a real(istic) project
- Even 1-2 weeks is enough
- Accounts for good days and bad days
- Need to have some idea of initial average velocity

---

# Case study: 2 week spreadsheet replacement project
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
- But you still need to read the code!
- It's super easy to "skim" the code
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
  - "Please make this code clearer and more concise"

---

# Learning when it's time to take the wheel
- Failing three times is a good rule of thumb
- You might see patterns in what it fails at

---

# LLM tarpits
## If it's confusing you, its' confusing the LLM...
- Some parts of any tech stack are just not intuitive
- Some tech stacks are more intuitive than others
- Documentation can help
  - Project specific AGENTS.md
- Examples are even better
- **Simplifying your code will pay off even more now**

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
- **You likely need to plan for more availability from the "deciders"**
- XP "On-Site Customer"

---

# Example: 2 week experiment
- The CEO was the "product owner"
- He only had so much time to give us
  - Sometimes we had to guess
  - We kinda got away with it ;)

---

# Tips and observations

---

# Don't sleep on old skool code generators!
- Yes, LLMs can generate code
**BUT**
- Code generators can generate code
  - ***The same way every time***
- And LLMs can run code generators

---

# Language choice matters
- Readability matters
- Paradigms with less context (FP) do better

---

# The data we have seems to back this up...
![language comparison](/images/exp_acb.png)

---

# Model choice also matters
- We've consistently seen best results from Claude
- but you should absolutely decide for yourself!

---

# Models seem to be plateauing
- Claude 3.5 -> 3.7 was amazing
- 3.7 -> 4.1 a bit less
- 4.1 -> 4.5 meh
- OpenAI reports seem similar
- **But this is good news**
  - We can pause and figure how to use this stuff

---

# Platform/framework choice also matters
- The less code there is, the less mistakes there are
  - true for humans **and** LLMs
  - LLMs make mistakes faster
- Some communities are embracing LLM coding agents

---

# Our favorite stack: Elixir and Phoenix
- Elixir
  - Expressive, functional language for the Erlang VM
- Phoenix
  - Full-stack Elixir framework inspired by Ruby on Rails
  - LiveView lets us write SPAs in Elixir

---

# Two approaches to AI coding
- An editor with AI integration
  - Github Co-Pilot
  - Cursor
  - Claude code (in VSCode)
- Async agents
  - Devin
  - Claude code (in a github action)

---

# In editor
- Better for fine-grained work
- You can see what's happening and intervene
- Can be boring to watch it flail about

---

# Coding agents in the cloud
- Larger more course grained task
- Let's you do more in parallel
- **Make sure they run in your environment**
  - Many existing AI coding agents do not
  - Claude code with GH actions does

---

# Tips for both
- Make sure it writes and runs tests
  - All of them, every time
  - But you may need to curb it's enthusiasm
- Refactor!
  - Don't accept spaghetti
  - With tests, it can often improve it's own code

---

# Follow the conventions!
- The LLM will almost always guess conventionally
- LLMs are like adding a new dev to your team every day :)
  - you need to tell it about any non-standard things *every time*
  - docs can help here, but only so much
- Example: REST APIs

---

# A picture is worth 1000 ~~words~~ tokens
- AI is astonishly good implementing a UI from mocks
- Seems to work regardless of specific tech
  - HTML/CSS, React, Rails, Elixir/Phoenix
- Could be a Figma mock, or a picture of a napkin
- Pretty good at fixing what it doesn't get quite right

---

# Using a DSL: Domain specific languages
- Example: a set of UI components
- Prompt LLM to generate screens using only these components
- Smaller sandbox, less mess

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

# LLM specific docs
- Some communities are adding this
  - Elixir libs ship with an agents.md
  - mix tasks can consolidate them for dependencies
- Claude skills are similar

---

# What's all this mean for us?

---

# The era of giant software teams may be over
- This is a *good* thing
- Software has inverse economies of scale
- Small teams have always been faster
  - Now they can do waaaay more

---

# It's time to revisit Buy vs Build
- Since almost forever, it's *always* been cheaper to buy
- Convestionally wisdom: buy, even it's not a perfect fit
  - Bloated, expensive ERP
  - Massively expensive implemenations that fail
- Building custom exact fit software is much more doable
- This could lead to *massive* growth in software development

---

# The job market is terrible for less experienced devs
- This *must* be temporary
  - Or our industry will not survive
- We are actively working to restart our apprenticeship program
- Hopefully others will follow suit

---

# For next time..
- We are gonna build project together!
  - Using in-editor AI and agents
- Let's discuss ideas
- Get ready to Embrace the Chaos!
- Starting repo: https://github.com/launchscout/acm_uc_demo
  - Elixir/Phoenix
  - Includes a devcontainer

---

<div style="display: flex; justify-content: space-around; align-items: center;">
  <div style="text-align: center;">
    <h3>Demo repo</h3>
    <p>github.com/launchscout/acm_uc_demo</p>
    <img src="/qrcode-github.svg" style="height: 300px;" />
  </div>
  <div style="text-align: center;">
    <h3>These slides</h3>
    <p>github.com/launchscout/ai-part-deux</p>
    <img src="/qrcode-slides.svg" style="height: 300px;" />
  </div>
</div>
