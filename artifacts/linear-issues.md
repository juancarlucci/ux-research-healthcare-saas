# Linear Issues — Patient Portal Research

This document tracks the Linear issues created from patient portal observations and analysis.

---

## Active Issues

### DYN-13825: Patient Portal — Hidden vs. Guided Booking Paths Create Practitioner Assignment Confusion

**Priority:** High  
**Status:** Awaiting Review → **Team Validated**  
**Created:** January 6, 2025  
**Team Response:** January 13, 2025

**Summary:**  
Critical finding — the booking portal has two completely different entry paths (guided vs. direct practitioner selection), but only one is explained. The higher-confidence path (direct selection) is hidden, leaving patients uncertain about "who am I seeing?" throughout the booking flow.

**Team Validation:**
JL independently reproduced the issue and confirmed the practitioner name doesn't appear in appointment summary throughout Path 1. Discussion ongoing about bringing Path 2 clarity into Path 1 or guiding more users to Path 2.

**Linear:** https://linear.app/DynaFlow/issue/DYN-13825/

**Evidence:**
- [observations/02-patient-variation-critical-findings.md](../observations/02-patient-variation-critical-findings.md)
- [synthesis/patterns.md - Pattern 2](../synthesis/patterns.md)

---

### DYN-13826: Patient Portal — "Complete Your Forms" Requirement Not Enforced, Creates Ambiguity

**Priority:** Medium  
**Status:** Awaiting Review → **Design Trade-off Identified**  
**Created:** January 6, 2025  
**Team Response:** January 13, 2025

**Summary:**  
The patient portal displays "You need to complete forms" but doesn't enforce this requirement. Patients can book additional appointments without completing forms, creating confusion about what's actually required vs. recommended.

**Team Context:**
JL revealed this is an intentional "soft enforcement" strategy to maximize form completion without forcing abandonment. Discussion ongoing about adding clarity on consequences while preserving the nudge effect.

**Linear:** https://linear.app/DynaFlow/issue/DYN-13826/

**Evidence:**
- [observations/03-patient-post-booking-experience.md](../observations/03-patient-post-booking-experience.md)
- [synthesis/patterns.md - Pattern 1](../synthesis/patterns.md)

---

### DYN-13827: Patient Portal — That First Moment — Where Do I Actually Start?

**Priority:** Low  
**Status:** Awaiting Review → **Solution Development Active**  
**Created:** January 6, 2025  
**Team Response:** January 13, 2025

**Summary:**  
First-time patients experience slight visual density and competing entry points on the landing page. Multiple elements compete for attention, creating mild cognitive load before the first action. Medium-confidence pattern that may benefit from testing before prioritization.

**Team Collaboration:**
JL and GQ collaboratively explored solutions using Claude. Team consensus emerging around "Option 2" (reframe "Any practitioner" card as "Choose by service" with service-focused subtitle and icon). YA agreed on direction.

**Linear:** https://linear.app/DynaFlow/issue/DYN-13827/

**Evidence:**
- [observations/01-patient-first-pass.md](../observations/01-patient-first-pass.md)
- [observations/02-patient-variation-critical-findings.md](../observations/02-patient-variation-critical-findings.md)
- [synthesis/patterns.md - Pattern 3](../synthesis/patterns.md)

---

## Issue Status Legend

- **Awaiting Review:** Created, waiting for team grooming
- **In Progress:** Actively being worked on
- **Done:** Implemented and deployed

---

**Last Updated:** January 6, 2025