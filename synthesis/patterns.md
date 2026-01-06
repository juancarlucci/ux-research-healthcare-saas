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

### Pattern 2: Practitioner Assignment Clarity

**Observed in:**
- First patient pass: "Am I booking with Manolo or Dr. Escobar?"

**Description:**  
When users select a service, add an add-on, and then see time slots for multiple practitioners, the mental model breaks down. It's unclear whether:
- The main service is with one practitioner and the add-on with another
- Both are with the same practitioner
- The system will assign automatically

**Impact:**  
**This is the highest-confidence friction point so far.** In healthcare, "who am I seeing?" is a trust-critical question. Ambiguity here may cause abandonment.

**Hypothesis:**  
Explicit practitioner assignment (with clear visual/textual confirmation) throughout the flow would eliminate a major trust gap.

**Needs validation:**  
- Does this confusion repeat in variation passes?
- How does this work when practitioners are interchangeable vs. when patients have preferences?

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
| System state visibility | Medium | 1 pass, multiple moments | Validate in variation passes |
| Practitioner clarity | High | Strong single moment | Validate immediately |
| Entry point | Low | Single moment, may be personal | Needs more data |

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