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

**Linear:** - Issue DYN-13825: [Patient Portal: Hidden vs. Guided Booking Paths Create Practitioner Assignment Confusion]

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

**Linear:** - Issue DYN-13826: [Patient Portal: "Complete Your Forms" Requirement Not Enforced, Creates Ambiguity]
 
- Issue DYN-13827: [Patient Portal: That First Moment — Where Do I Actually Start?]

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

**Linear:** - Issue DYN-13827: [Patient Portal: That First Moment — Where Do I Actually Start?]

**Evidence:**
- [observations/01-patient-first-pass.md](../observations/01-patient-first-pass.md)
- [observations/02-patient-variation-critical-findings.md](../observations/02-patient-variation-critical-findings.md)
- [synthesis/patterns.md - Pattern 3](../synthesis/patterns.md)

---

### DYN-13913: Practitioner Onboarding — Auto-Redirect to Setup Wizard After First Login

**Priority:** High  
**Status:** Triage/Waiting  
**Created:** January 15, 2026  

**Summary:**  
The Setup Wizard is well-designed and provides excellent structured onboarding for new practice owners — but it's hidden behind a cluttered dashboard. New practitioners land on visual chaos after first login instead of being guided to the good onboarding that already exists.

**Key Finding:**  
This is a **sequencing problem, not a quality problem.** The product demonstrates it knows how to create effective onboarding. It's just presented in the wrong order.

**Recommendation:**  
Auto-redirect new practitioners to Setup Wizard after first login (routing change, not rebuild). After wizard completion, then show dashboard — at which point they'll have context.

**Impact:** High impact, low effort — leverages existing good work.

**Linear:** DYN-13913: [Practitioner Onboarding — Auto-Redirect to Setup Wizard After First Login]

**Evidence:**
- [observations/04-practitioner-first-registration.md](../observations/04-practitioner-first-registration.md)
- [observations/05-practitioner-setup-wizard.md](../observations/05-practitioner-setup-wizard.md)
- [synthesis/patterns.md - Pattern 7](../synthesis/patterns.md)

---

### DYN-13924: Practitioner Dashboard — Visual Hierarchy Creates Cognitive Overload on First Login

**Priority:** Medium  
**Status:** Triage/Waiting  
**Created:** January 15, 2026  

**Summary:**  
After first login, the practitioner dashboard presents multiple competing visual elements (stale "November Updates" button, oversized text, badges) while the critical next steps (Setup Wizard, Settings) have minimal visual weight. Creates cognitive overload when clarity is needed most.

**Key Finding:**  
The two most important actions have the least visual prominence. Practice owners must scan through visual noise to find what actually matters.

**Recommendation:**  
Restructure visual hierarchy to prioritize Setup Wizard as focal point. Alternative: Auto-redirect (see DYN-13913).

**Impact:** Medium-high — affects first impression and onboarding confidence.

**Linear:** DYN-13924: [Practitioner Dashboard — Visual Hierarchy Creates Cognitive Overload on First Login]

**Evidence:**
- [observations/04-practitioner-first-registration.md](../observations/04-practitioner-first-registration.md)
- [synthesis/patterns.md - Pattern 5](../synthesis/patterns.md)

**Related:** DYN-13913 (Auto-redirect addresses same problem)

---

### DYN-[13927]: Practitioner Login — Page Speaks to Patients Instead of Practice Owner After Registration

**Priority:** Medium  
**Status:** Triage/Waiting  
**Created:** January 15, 2026  

**Summary:**  
After completing registration and launching their practice, new practice owners land on a login page with entirely patient-facing messaging ("make your next appointment, view existing appointments"). No acknowledgment of their role as practice owner.

**Key Finding:**  
Creates doubt at critical trust moment: "Am I in the right place? Is this how practitioners log in?"

**Recommendation:**  
Context-aware messaging for first-time practice owner login, or visual separation between practice owner/staff login and patient access.

**Impact:** Medium — affects trust at critical handoff after payment.

**Linear:** DYN-[13927]: [Practitioner Login — Page Speaks to Patients Instead of Practice Owner After Registration]

**Evidence:**
- [observations/04-practitioner-first-registration.md](../observations/04-practitioner-first-registration.md)
- [synthesis/patterns.md - Pattern 4](../synthesis/patterns.md)

**Related:** Part of broader System State Visibility Gap pattern (Pattern 1)

---

## Issue Status Legend

- **Awaiting Review:** Created, waiting for team grooming
- **In Progress:** Actively being worked on
- **Done:** Implemented and deployed

---

**Last Updated:** January 6, 2025