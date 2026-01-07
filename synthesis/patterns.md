# Patterns & Themes

This document synthesizes patterns across multiple observation sessions. It evolves as more data comes in.

---

## Status

**Last Updated:** January 6, 2025  
**Observations Synthesized:** 1 (First patient pass)  
**Confidence Level:** Early — patterns emerging but need validation

---

## Emerging Patterns

### Pattern 1: System State Visibility Gap

**Observed in:**
- First patient pass: "Am I done setting up?"
- First patient pass: Login gate timing question

**Description:**  
Users frequently ask themselves (implicitly): "Is this complete? What's required vs. optional? What happens next?"

The system provides functional completeness but doesn't always make state explicit to users.

**Impact:**  
Creates low-level uncertainty that accumulates. Users can usually figure it out, but it costs cognitive energy and confidence.

**Hypothesis:**  
Making system state more visible (progress indicators, explicit "required/optional" signals, "what's next" guidance) would reduce cognitive load without adding complexity.

**Needs validation:**  
- Does this repeat in practitioner onboarding?
- Is this worse for first-time users vs. returning users?

---

### Pattern 2: Practitioner Assignment Clarity ⚠️ CRITICAL

**Observed in:**
- First patient pass: "Am I booking with Manolo or Dr. Escobar?"
- Second patient pass: "Why am I getting a massage with Emily? Is Graham doing acupuncture?"
- Deep exploration: Discovered dual-path system

**Description:**  
The system has **two completely different booking paths** but only explains one:

**Path 1 (System-Guided):** Location → Service → Date/Time
- Instruction: "Choose a service first then choose a practitioner"
- Practitioner is inferred from location (never shown in summary)
- Creates ongoing uncertainty about "who am I seeing?"

**Path 2 (Hidden):** Direct practitioner selection via image click
- No instruction provided
- Practitioner appears immediately with photo + bio
- Builds confidence early, maintains throughout

**The better path is hidden. The visible instruction contradicts the visual affordance.**

**Impact:**  
**CRITICAL TRUST GAP in healthcare context.** 

In healthcare, "who is treating me?" is a primary concern. Path 1 leaves this question unanswered throughout the entire flow. Users must infer practitioner from location.

Path 2 solves this completely but is only discoverable by accident.

**Validation Status:** ✅ **CONFIRMED**  
- Tested both paths multiple times
- Pattern repeats consistently
- Impact on trust validated

**Recommendation Priority:** **P0 - Immediate**

**Hypothesis:**  
Making both paths explicit ("Do you have a practitioner in mind? [Yes] [Not yet]") and showing practitioner name in Path 1 summary would eliminate the highest-impact trust gap in the current flow.

---

### Pattern 3: Entry Point Discoverability

**Observed in:**
- First patient pass: Hovering at "Any practitioner / Choose a service first"

**Description:**  
The first interaction moment includes mild confusion about "what starts the flow?" The interface presents options, but sequence isn't immediately obvious.

**Impact:**  
Creates slight initial cognitive load. Not blocking, but requires "figuring out" rather than guiding. Works for motivated/tech-comfortable users but may increase hesitation for others.

**Hypothesis:**  
Clearer entry point signaling (visual hierarchy, progressive disclosure, or explicit instruction) could smooth the first moment.

**Needs validation:**  
- How does this vary across different entry paths?
- Is this worse on mobile?

---

## Moments of Clarity (What Works)

### Clarity Moment 1: Seeing Actual Availability
**When:** Calendar view showing real time slots  
**Why it works:** Makes availability tangible, builds confidence  
**Keep:** This is a strong moment

### Clarity Moment 2: Login/Account Gate
**When:** After selecting service + time, before commitment  
**Why it works:** Timing feels appropriate, messaging is clear  
**Keep:** This is a strong moment

---

## Open Questions

Questions that need more observation to answer:

1. **Does practitioner confusion repeat?**  
   - Test with different paths (skipping add-ons, different practitioners)
   
2. **Is system state visibility worse in practitioner onboarding?**  
   - Practitioners are configuring, not just booking — does this compound the issue?
   
3. **How do returning users experience these flows?**  
   - Do patterns still hold, or do they only affect first-time users?
   
4. **Mobile vs. desktop?**  
   - Haven't tested mobile yet

---

## Pattern Confidence Levels

| Pattern | Confidence | Evidence | Next Step |
|---------|-----------|----------|-----------|
| System state visibility | Medium | 1 pass, multiple moments | Validate in practitioner flow |
| **Practitioner clarity** | **CRITICAL - Validated** | **2 passes, deep exploration, both paths tested** | **Ready for Linear issue** |
| Entry point | Medium | 2 passes, repeated | May be systemic |

---

## Next Synthesis Checkpoint

After 2-3 variation passes, revisit this document and:
- Promote patterns that repeat
- Demote patterns that don't
- Add new patterns if they emerge
- Decide what's ready for Linear issues

---

**Notes:**

This is a living document. Early patterns may dissolve. Strong patterns will strengthen. Trust the process.