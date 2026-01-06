# High-Impact Opportunities

This document translates observed patterns into business-level opportunities. These are **not UI prescriptions** — they're learning design opportunities that can inform product decisions.

---

## Status

**Last Updated:** January 6, 2025  
**Based on:** 1 patient observation pass  
**Confidence:** Early — these will sharpen with more data

---

## Opportunity 1: Clarify Practitioner Assignment Throughout Flow

### The Problem
Users experience uncertainty about "who am I booking with?" when:
- Selecting services that could be with different practitioners
- Adding add-ons that may be with different practitioners
- Viewing time slots from multiple practitioners simultaneously

This is the **highest-confidence friction point** identified so far.

### Why This Matters
In healthcare, "who am I seeing?" is a trust-critical question. Ambiguity at this moment:
- Erodes patient confidence
- May cause booking abandonment
- Undermines the professionalism of the practice

### The Opportunity
Make practitioner assignment explicit and consistent throughout the booking flow.

This could mean:
- Clear visual/textual confirmation after each selection
- Treating "practitioner choice" as a first-class decision point
- Surfacing practitioner info (name, specialty, photo) at key moments
- Distinguishing "any available" from "specific practitioner" clearly

### Success Metrics
- Reduced abandonment at booking confirmation
- Fewer support questions about "who am I scheduled with?"
- Increased patient confidence (measured via post-booking survey or NPS)

### Next Steps
- Validate this repeats in variation passes
- Understand how current logic assigns practitioners
- Explore if this is worse when services + add-ons have different providers

---

## Opportunity 2: Increase System State Visibility

### The Problem
Users frequently ask themselves:
- "Am I done?"
- "What's next?"
- "Is this required or optional?"
- "Did that save?"

The system is functional, but doesn't always make state explicit.

### Why This Matters
Uncertainty accumulates across the flow. Each moment of "wait, did that work?" costs cognitive energy and erodes confidence. This may not block motivated users, but it increases friction for:
- Less tech-comfortable patients
- Mobile users
- High-stress booking moments (urgent care)

### The Opportunity
Make system state more visible throughout the booking journey.

This could mean:
- Progress indicators ("Step 2 of 4")
- Explicit "required vs. optional" labeling
- Clear confirmation of saved state
- "What's next" guidance at transition points

### Success Metrics
- Reduced hesitation time at key decision points
- Fewer "back button" presses (users checking if previous step saved)
- Improved task completion rates for first-time users

### Next Steps
- Validate this repeats in practitioner onboarding (likely worse there)
- Identify specific moments where state is least clear
- Explore whether returning users experience this differently

---

## Opportunity 3: Strengthen Entry Point Guidance

### The Problem
The first moment of interaction includes mild confusion about:
- Where to start the flow
- What order to do things in
- What "Any practitioner / Choose a service first" means

### Why This Matters
First impressions set the tone. If the entry point requires "figuring out," it creates early cognitive load that carries forward. This works for motivated users but may increase abandonment for less engaged patients.

### The Opportunity
Make the entry point and initial sequence clearer.

This could mean:
- Stronger visual hierarchy for the primary CTA
- Progressive disclosure (show one step at a time)
- Explicit instruction ("Start by choosing a service")
- Reducing visual density on landing

### Success Metrics
- Reduced time-to-first-interaction
- Fewer users abandoning before first click
- Improved mobile conversion (likely more sensitive to this)

### Next Steps
- Validate with more users (confidence currently LOW)
- Test on mobile (may be more pronounced)
- Explore if this is personal preference vs. systemic

---

## Prioritization Framework

| Opportunity | Business Impact | User Pain | Confidence | Recommended Priority |
|-------------|----------------|-----------|------------|---------------------|
| Practitioner clarity | High | High | High | **P0 - Immediate** |
| System state visibility | Medium | Medium | Medium | **P1 - Near-term** |
| Entry point guidance | Low-Medium | Low | Low | **P2 - Validate first** |

---

## What's Not Here (Intentionally)

This document does NOT include:
- Visual design critiques
- Performance issues (unless they block understanding)
- Feature requests without learning rationale
- Edge cases
- Personal aesthetic preferences

If something's not here, it's because:
- It didn't affect learning or confidence
- It's too early to call it a pattern
- It's a bug, not a design opportunity

---

## Next Update

After 2-3 more observation passes, this document will:
- Promote opportunities with strong evidence
- Demote opportunities that don't validate
- Add new opportunities if they emerge
- Include specific moment examples (with screenshots)

---

**Note:** This is living analysis. Early hypotheses may not hold. Strong patterns will strengthen. The goal is clarity, not speed.