# The AI-Assisted Coding Journey
## From Skepticism to 4x Developer Productivity

---

## The Early Days: Skepticism and False Starts
### 2022-2023

- **First Experience**: GitHub Copilot
- **Initial Reaction**: "Lucy and Charlie Brown with the football"
  - Occasionally generated something great
  - More time reading generated code than writing it myself
  - "This AI thing is stupid"
- **The Skeptic's Dilemma**: Hope it was just hype that would blow over

> *"I really hope that AI would just be a hype train that would blow over and I could retire before I had to deal with it"* - Chris

---

## The Turning Point: Cursor Changes Everything
### Early 2025

- **The Catalyst**: Tim's success stories from Beyond Will
- **Key Breakthrough**: Cursor's Composer mode
- **The Milestone Moment**: 
  - AI runs tests
  - Sees test results  
  - Goes back and fixes code accordingly
  - **Self-correction capability**

> *"That's like the date when Skynet became self-aware... when I saw Cursor run the tests and fix the code"* - Chris

---

## Project 1: Paramount Landscaping
### The Two-Day Miracle

**The Challenge**: 
- Small landscaping company ($1-2M revenue)
- Custom work order sheets everyone hated
- Too small for traditional custom software

**The Experiment**:
- **Timeline**: 2 calendar days (~12-16 hours coding)
- **Goal**: Build a working prototype instead of wireframes
- **Stack**: Elixir, Phoenix, LiveView
- **Result**: Fully functional work order management system

---

## Paramount: Key Learnings

### What Worked:
- Test-driven development with AI
- AI could self-correct using test feedback
- Rapid iteration and deployment

### What Didn't:
- AI generated non-idiomatic code initially
- Required constant guidance on best practices
- Would ignore guidelines and "go rogue"

### The Pattern Emerges:
**Good development practices matter MORE with AI, not less**

---

## Project 2: A&P Calibration System
### Scaling Up the Process

**The Setup**:
- 2-week timeframe, 80 hours
- Replace Excel spreadsheet with web app
- Team: 1 developer (Chris) + 0.5 designer (Katie)

**The Innovation**:
- Story mapping session (2 hours vs planned 4)
- Hand-drawn sketches → Cursor → Working UI
- Designer using Cursor + Tailwind for first time

**Results**: Delivered everything plus "nice-to-have" features

---

## A&P: The Collaboration Breakthrough

### Designer + AI Workflow:
1. Katie sketches interface on iPad
2. Chris attaches image to Cursor
3. "Make the screen look like this"
4. **One-shot CSS generation** - amazingly close

### New Bottleneck Discovered:
- Development speed: ✅ Not the bottleneck
- **Client feedback cycles**: ❌ New bottleneck
- Need for "on-site customer" becomes critical

---

## Project 3: Mike Albert
### Enterprise Oracle Forms Migration

**The Challenge**:
- 300-400 Oracle Forms to convert
- Currently: 4-6 weeks per form
- Legacy XML + embedded PL/SQL
- React frontend + Go microservices backend

**The Architecture Problem**:
- No contract between frontend/backend
- Arbitrary JSON payloads
- Trial and error debugging took days

---

## Mike Albert: The OpenAPI Solution

### The Breakthrough Architecture:
1. **Generate OpenAPI spec first** (using Cursor)
2. **Use deterministic code generators**:
   - Go OpenAPI CodeGen → backend stubs
   - JavaScript OpenAPI CodeGen → REST client
3. **Cursor fills in the logic** within guardrails
4. **Result**: First-time success, no guessing

### Key Insight:
> *"Don't bring a knife to a gunfight. Use deterministic code generation when available."*

---

## The 4X Productivity Pattern

### Performance Metrics:
- **Typical estimation**: 4-5 cards per week
- **AI-assisted delivery**: 40 cards in 2 weeks
- **Average improvement**: 4X faster
- **Range**: 2X (conservative) to 10X (best case)

### Why 4X is an Average:
- Some days: 10X+ productivity
- Some days: AI makes a mess, slower than manual
- Need sufficient time blocks to average out the chaos

---

## Technical Insights: Language Matters

### Ruby: The AI Sweet Spot
- Almost like writing pseudocode
- "I don't know how to write this, but if I did, I would write it like this"
- High corpus of training data
- Intuitive syntax allows for successful "guessing"

### Elixir: Functional Advantage
- Bounded context (function parameters + return value)
- No complex object graphs
- Easier for AI to understand full context
- Similar benefits to why apprentices learn functional programming well

---

## The Guardrails Framework

### What Works:
1. **Test-Driven Development** - AI can self-correct
2. **Examples over Documentation** - Show, don't tell
3. **Deterministic Code Generation** - Use existing tools
4. **API Contracts** - OpenAPI specifications
5. **Bounded Context** - Clear sandboxes for AI

### What Doesn't Work:
- Long documentation that AI ignores
- Hoping AI will follow complex patterns
- Letting AI run wild without constraints

---

## Lessons Learned: Good Practices Matter More

### Classic XP Principles Amplified:
- **Test-Driven Development**: Critical for AI self-correction
- **On-Site Customer**: Feedback bottleneck becomes critical
- **Simple Design**: "If it's clever, throw it out"
- **Continuous Integration**: Deploy early and often

### New Insight:
> *"Programming is a force multiplier. Unless you're applying the force correctly, you're going to break stuff."*

---

## The Mindset Shift

### From Fear to Tool:
- **Fear**: AI will replace developers with garbage code
- **Reality**: AI augments developers to write better code faster
- **Key Realization**: "It makes me feel like Superman"

### The Binary Switch:
- Junior developers: Eager to experiment
- Senior developers: Holding at arm's length
- **Solution**: Demonstrate value through pair/mob programming

---

## Current Experiments: Mob Programming

### Mike Albert Sessions:
- 3-4 developers on big monitor
- First sessions: Chris driving, others guiding
- Recent sessions: Their devs driving
- **Goal**: Knowledge transfer and mindset shift

### Freight Workshop (Upcoming):
- Previous client, familiar domain
- Discovery + mob programming sessions
- Focus on developer transformation

---

## Future Opportunities

### 1. Developer Augmentation Services
- Help organizations adopt AI effectively
- Facilitate the mindset shift
- Train teams on best practices

### 2. Accessible Custom Software
- Companies like Paramount: too small for traditional custom software
- 10X cost reduction makes custom software viable
- "Bespoke ERPs" for mid-range companies

### 3. Legacy System Modernization
- Previously cost-prohibitive migrations
- Oracle Forms → Modern stacks
- Massive technical debt becomes manageable

---

## Key Takeaways

### For Organizations:
1. **Start with existing good practices** - they matter more now
2. **Invest in developer training** - not just tools
3. **Focus on feedback cycles** - new bottlenecks emerge
4. **Embrace the averaging** - some days are 10X, some are 0.5X

### For Developers:
1. **Learn to prompt effectively** - specific examples work best
2. **Use guardrails** - contracts, specs, tests
3. **Combine tools** - AI + traditional code generation
4. **Stay in control** - you're the architect, AI is the implementer

---

## The Future is Already Here

### Current Reality:
- 4X productivity improvements are achievable today
- Good development practices are more important than ever
- The bottleneck has shifted from coding to collaboration

### The Challenge:
> *"AI moves really fast, but humans move really slowly"*

### The Opportunity:
**Help organizations and developers make the transition successfully**

---

## Thank You

### Questions?

*"The things that we value about doing software development well still matter. They matter more now."* 