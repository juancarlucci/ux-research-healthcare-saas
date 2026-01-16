# Patient Portal — First-Time User Pass

**Date:** January 5-6, 2025  
**Role:** First-time patient  
**Environment:** Production (JL's demo practice)  
**URL:** https://lila.HealthFlow.app/portal/booking/

---

## Session Overview

This was my first pass through the patient booking portal, approaching it with zero context as a new patient seeking care. The goal was to observe how the system teaches itself, where confidence builds or breaks, and what mental models are implied vs. supported.

---

## Key Observations

### Observation 1: Initial Orientation

#### Context
Landing on the booking portal for the first time.

#### Expectation
As a patient, I expected to immediately understand: "This is where I book an appointment" and see a clear starting point.

#### Reality
The page presents as a patient portal (correct), but visual density and multiple entry points created slight overwhelm. The "Any practitioner" button felt like the entry point, but the instruction "Choose a service first then choose a practitioner" created initial confusion about sequence.

#### Impact
First impression includes mild cognitive load. Not blocking, but requires patients to "figure it out" rather than being guided. This works for motivated users but may increase hesitation for less tech-comfortable patients.

#### Opportunity
This is a moment where system state and flow guidance could be more explicit. Making the entry point and sequence clearer could reduce early cognitive load.

---

### Observation 2: Service Selection Clarity

#### Context
After clicking into the flow, presented with service selection.

#### Expectation
I expected to see services with enough context to make an informed choice.

#### Reality
Seeing actual time slots in the next week was the moment clarity noticeably increased. The calendar view made availability tangible.

#### Impact
This is a confidence-building moment. Patients can see "yes, there's real availability soon."

#### Opportunity
This moment works well. Consider how to surface this clarity earlier in the flow.

---

### Observation 3: Practitioner Assignment Confusion

#### Context
After selecting a service and add-on, then choosing a date/time.

#### Expectation
I expected the system to be clear about whether I'm booking with a specific practitioner or "any available."

#### Reality
The interface showed time slots for multiple practitioners simultaneously, and my appointment summary showed "Manolo Del Toro" after I'd selected him for the add-on, but it wasn't immediately clear if the main service was also with Manolo or with Dr. Escob (whose name appeared in other contexts).

#### Impact
**Biggest confusion moment.** This creates uncertainty about "who am I actually seeing?" which matters enormously for trust in healthcare. Patients may abandon or lose confidence at this point.

#### Opportunity
Making practitioner assignment explicit and consistent across the flow would eliminate a major trust gap. This is where "functional" and "learnable" diverge most clearly.

---

### Observation 4: Commitment Gate

#### Context
After selecting date/time, presented with login/account creation requirement.

#### Expectation
Expected to need an account, but timing felt appropriate.

#### Reality
The countdown timer (24:48) and "You are not done yet" messaging felt reasonable, not stressful. The gate made sense.

#### Impact
This moment works well. No drop in confidence. The timer creates light urgency without pressure.

#### Opportunity
This is a strong moment. No changes needed.

---

## Overall Takeaway

**As a first-time patient, I would complete the booking.**

While the flow felt bumpy at moments and required some figuring out, I ultimately felt capable of moving forward and confident that I was close to success.

**The system is functional, but relies on user persistence.**

This works for motivated patients seeking care, but leaves opportunity to reduce cognitive load and increase confidence — especially around practitioner clarity and initial flow orientation.

---

## Patterns to Watch

These moments repeated or stood out as potentially systemic:

1. **System state visibility** — "Am I done? What's next? What's optional?"
2. **Practitioner assignment clarity** — "Who am I booking with?"
3. **Entry point guidance** — "Where do I start?"

---

## Next Steps

- [ ] Run variation passes (different paths, practitioners, scenarios)
- [ ] Observe if practitioner confusion repeats
- [ ] Document when clarity increases vs. decreases
- [ ] Prepare structured synthesis for Linear issues

---

**Status:** Complete, settled  
**Ready for synthesis:** Yes