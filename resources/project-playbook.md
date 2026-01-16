# HealthFlow Learning Design — Project Playbook

This is your "how we work" guide. Reference this whenever you need clarity on methodology, voice, workflow, or decision-making.

---

## 🎯 Project Mission

Improve the learning and onboarding experience for HealthFlow (patient portal and practitioner setup) through systematic observation, pattern synthesis, and actionable feedback.

**Primary goals (ranked):**
1. Get HealthFlow work done efficiently
2. Build portfolio evidence of LD/DevEx skills
3. Create reusable templates for future projects
4. Demonstrate technical sophistication

---

## 🧠 Core Methodology: The 5-Part Observation Framework

Every structured observation uses this framework to keep feedback at the learning/product level (not UI nitpicking):

### 1. **Context** — Where am I?
What step/flow/mindset is the user in?

### 2. **Expectation** — What I thought would happen
What mental model does the UI imply?

### 3. **Reality** — What actually happened
What did the product actually do?

### 4. **Impact** — Why this matters
Connect to business value: adoption, confidence, trust, retention.

### 5. **Opportunity** — Not a solution, a direction
Suggest learning intent, not UI prescription.

**Templates:**
- `observations/templates/observation-template.md` (structured observations)
- `observations/templates/session-log-template.md` (quick capture during sessions)

---

## ✍️ Voice & Tone Guidelines

You have two primary writing voices depending on context:

### **Professional/Formal Voice** (Linear Issues, High-Stakes Findings)

**When to use:**
- Critical or high-priority Linear issues
- Findings that need executive/engineering buy-in
- Technical documentation
- Formal reports or deliverables

**Characteristics:**
- Clear, direct, structured
- Business-level framing (trust, conversion, operations)
- Evidence-based recommendations
- Minimal metaphor, maximum clarity

**Example opening:**
> "The patient booking portal has two completely different entry paths, but only one is explained to users..."

---

### **Conversational/Empathetic Voice** (Exploratory Issues, Reflections)

**When to use:**
- Medium/low-priority findings
- Exploratory or uncertain patterns
- Personal reflections in journal
- Informal communication with team

**Characteristics:**
- Warm, engaging, empathetic
- Vivid metaphors and accessible language
- Acknowledges uncertainty
- Feels like a kind guide

**Example opening:**
> "When someone lands on the booking portal for the first time, they're hit with a lot at once... It's not broken. But it's *dense*."

**Signature moves:**
- Metaphors: "like turning on stadium floodlights before I've found the door"
- Contrasting pairs: "Heavy or light? Foggy or clear?"
- Gentle authority: "This isn't a deal-breaker, but..."
- Care-focused: "The goal is to make the front door feel welcoming"

**Full voice guide:** See chat transcript for "Juan Carlos's Professional/Technical Writing Voice (Voice 3)"

---

## 🗂️ File Organization Strategy

### **Working Layers:**

#### **Layer 1: Active Work (GitHub - Local)**
```
observations/          → Raw observation data (timestamped, structured)
synthesis/            → Analysis, patterns, high-impact opportunities
artifacts/            → Final deliverables (Linear issues, reports)
resources/            → Context, role definition, reference docs
journal/              → Private notes (gitignored)
```

#### **Layer 2: Coordination (Notion)**
- Task tracking (daily work)
- Quick capture notes
- Calendar/timeline view
- Links to GitHub files

#### **Layer 3: Delivery (Linear)**
- Actionable issues for HealthFlow team
- Business-level framing
- Ready for grooming/prioritization

**Data flow:** 
Observation session → Session log (Notion) → Structured observation (GitHub) → Pattern synthesis (GitHub) → Linear issue → Team action

---

## 📝 Observation Session Workflow

### **Before Session:**
1. Copy `observations/templates/session-log-template.md`
2. Create new file: `observations/[##]-[descriptive-name].md`
3. Review goals: What am I specifically observing?

### **During Session:**
- 🐢 Go slow, deliberate
- 🧘 Stay in user role (patient or practitioner)
- 📝 Capture in session log (Notion or scratch file)
- ⏸️ Pause at hesitation moments
- ❓ Notice questions that arise internally

**What NOT to log:**
- Visual design preferences
- Performance issues (unless blocking understanding)
- Edge cases or feature completeness

**What TO log:**
- Confusion, uncertainty, cognitive overload
- Missing explanations or unclear system state
- Moments of hesitation or lost confidence
- Trust erosion or building

### **After Session (15-30 min):**
1. Convert raw notes to structured observations (5-part framework)
2. Update `synthesis/patterns.md` if patterns strengthen
3. Add to Notion task notes (quick summary)

### **End of Week:**
- Synthesize themes
- Decide what's ready for Linear issues
- Identify what needs more validation

---

## 🎫 Creating Linear Issues

### **When to Create Issues:**
- Pattern validated across 2+ sessions
- Business impact is clear
- Confidence level is Medium or High
- Team can act on the recommendation

### **Issue Structure:**
```markdown
# [Clear Title]

## Context
Brief description of user scenario and where this occurs.

## What Users Experience
Observable behavior from user's perspective.

## Impact
Why this matters for:
- User confidence/trust
- Business goals (adoption, retention)
- Practice operations

## Recommendation
High-level direction (NOT detailed UI prescription).

## Evidence
- GitHub observation: [link]
- Pattern analysis: [link]
- Confidence level: [High/Medium/Low]
```

### **Priority Guidelines:**
- **High/Urgent:** Critical trust issues, validated patterns, clear business impact
- **Medium:** Operational friction, medium-confidence patterns
- **Low:** Optimizations, exploratory findings, needs validation

### **Labels to Use:**
- ✅ Enhancement (design/experience improvements)
- ✅ UX/UI (user experience issues)
- ✅ To Groom (needs team discussion)
- ✅ Touches Registration (if relevant to onboarding)

---

## 🔄 Git Workflow

### **Commit Message Format:**
Follow Conventional Commits:
```
type(scope): description

Examples:
feat(templates): create 5-part observation framework template
docs(observations): add first-time patient booking pass analysis
docs(synthesis): elevate practitioner clarity to critical validated pattern
chore(config): add gitignore for sensitive files
```

**Common types:**
- `feat` - New capability or template
- `docs` - Documentation (observations, synthesis, artifacts)
- `chore` - Maintenance (config, cleanup)
- `fix` - Corrections

### **Commit Frequency:**
- One commit per logical unit (per file is good)
- Meaningful messages (no "update" or "changes")
- Push regularly (don't accumulate)

---

## 💬 Communication Patterns

### **With GQ (CEO):**
- Focus on business value and actionable insights
- Frame at product/adoption/trust level
- Linear issues are primary deliverable
- Offer sync or async (give him control)

### **With JL (Engineer):**
- More casual, collaborative tone
- Can get technical if needed
- Willing to review process/methodology
- Open to detailed questions

### **General Principle:**
Lead with value, not process. Show what you found, not how hard you worked.

---

## 🧰 Tool Usage

### **GitHub (Primary Working Environment)**
- All structured observations
- Pattern synthesis and analysis
- Final artifacts (reports, Linear issue tracking)
- Version controlled, portfolio-ready

### **Notion (Coordination Layer)**
- Task tracking and daily work
- Quick capture during sessions
- Calendar view for deadlines
- Links to GitHub files

### **Linear (Delivery Layer)**
- Actionable issues for team
- Business-level framing
- Connected to Project Management
- Ready for grooming

### **Claude (Research Assistant)**
- Methodology guidance
- Document creation
- Voice/tone adjustment
- Strategic thinking partner

---

## 🎨 Design Principles

### **What This Work IS:**
- Observing how people learn the system
- Identifying where understanding breaks down
- Framing opportunities at business/product level
- Bridging user experience → product decisions

### **What This Work IS NOT:**
- UI design or visual critiques
- Feature requests without learning rationale
- Bug reporting (unless it blocks understanding)
- Prescribing specific solutions

### **North Star:**
"I am not reviewing the product — I am observing how people learn it."

---

## 🚦 Decision Frameworks

### **When to Create a Linear Issue:**
✅ Pattern repeats across sessions  
✅ Business impact is clear  
✅ Confidence is Medium or High  
✅ Team can take action  

❌ One-time observation  
❌ Personal preference  
❌ Low confidence / needs validation  

### **When to Continue Research vs. Deliver:**
**Continue research if:**
- Patterns are still emerging
- Low confidence in findings
- Need more user perspectives

**Deliver now if:**
- High-confidence, validated patterns exist
- Team is waiting for feedback
- You can ship value while continuing research

### **When to Use Which Voice:**
**Formal/Professional:**
- Critical findings
- High-priority issues
- Technical documentation

**Conversational/Empathetic:**
- Exploratory findings
- Medium/low priority
- Uncertain patterns

---

## 📊 Success Metrics

### **For HealthFlow:**
- Actionable Linear issues created
- Patterns validated and prioritized
- Business value clearly framed
- Team can make product decisions

### **For Portfolio:**
- Methodology documented and repeatable
- Evidence of systematic LD/DevEx work
- Range demonstrated (formal + conversational)
- GitHub repo is portfolio-ready

### **For Personal Growth:**
- Confidence in observation methodology
- Ability to frame findings at business level
- Building reusable templates
- Demonstrating bridge role (user ↔ product ↔ eng)

---

## 🎯 Current Focus Areas

**Patient Portal (In Progress):**
- ✅ Booking flow patterns identified
- ✅ Linear issues created
- 🔄 Post-booking experience documented
- ⏭️ Recurring appointments edge case

**Practitioner Onboarding (Next):**
- Registration and setup flow
- Configuration clarity
- Mental model formation
- Trust building in setup process

---

## 📚 Key Resources

**Templates:**
- `observations/templates/observation-template.md`
- `observations/templates/session-log-template.md`

**Methodology:**
- `resources/role-definition.md` (what this role is)
- `resources/HealthFlow-context.md` (project background)

**Current Work:**
- `synthesis/patterns.md` (emerging themes)
- `synthesis/high-impact-opportunities.md` (business-level recommendations)
- `artifacts/linear-issues.md` (tracking deliverables)

**Status:**
- `STATUS.md` (current state, next steps)

---

**Last Updated:** January 6, 2025  
**Version:** 1.0