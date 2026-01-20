# Patterns & Themes

This document synthesizes patterns across multiple observation sessions. It evolves as more data comes in.

---

## Status

**Last Updated:** January 15, 2026  
**Observations Synthesized:** 4 (3 patient sessions, 1 practitioner registration)  
**Confidence Level:** Patterns emerging with strong validation across user types

---

## Emerging Patterns

### Pattern 1: System State Visibility Gap ⬆️ **ELEVATED — CRITICAL**

**Observed in:**
- First patient pass: "Am I done setting up?"
- First patient pass: Login gate timing question
- **Practitioner registration: "Almost Done" page confusion**
- **Practitioner registration: Login page role confusion**

**Description:**  
Users frequently ask themselves: "Is this complete? What's required vs. optional? What happens next? Am I in the right place?"

The system provides functional completeness but doesn't consistently make state explicit to users.

**NEW EVIDENCE (Practitioner Flow):**
- After payment, "Almost Done" page says "Check your email" but also offers demos, signup (already signed up), and full site navigation — creates uncertainty about completion
- First-time practice owner login page speaks entirely to patients ("make your next appointment") with no acknowledgment of role — creates doubt: "Am I logging in correctly?"

**Impact:**  
Creates cumulative uncertainty that erodes confidence at critical trust moments. Pattern appears in BOTH patient and practitioner flows, suggesting it's systemic rather than flow-specific.

**Validation Status:** ✅ **CONFIRMED — CRITICAL**  
Repeats across user types (patient, practitioner), multiple touchpoints (booking, onboarding, login)

**Hypothesis:**  
Making system state and user role more visible (progress indicators, explicit role acknowledgment, clear "what's next" at handoffs) would reduce cognitive load and build confidence.

**Recommendation Priority:** **P0 - High Impact**

---

### Pattern 2: Practitioner Assignment Clarity ⚠️ CRITICAL — VALIDATED

**Observed in:**
- First patient pass: "Am I booking with Manolo or Dr. Escobar?"
- Second patient pass: "Why am I getting a massage with Emily? Is GQ doing acupuncture?"
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
- **Linear issue created: DYN-13825**
- **Team validated independently (JLreproduced issue)**

**Recommendation Priority:** **P0 - Immediate** (Currently being addressed by team)
---

### Pattern 3: Entry Point Discoverability

**Observed in:**
- First patient pass: Hovering at "Any practitioner / Choose a service first"
- Second patient pass: "Are we telling them to choose a service first but we don't show services?"

**Description:**  
The first interaction moment includes mild confusion about "what starts the flow?" The interface presents options, but sequence isn't immediately obvious.

**Impact:**  
Creates slight initial cognitive load. Not blocking, but requires "figuring out" rather than guiding. Works for motivated/tech-comfortable users but may increase hesitation for others.

**Validation Status:** Medium confidence  
- Observed consistently
- **Linear issue created: DYN-13827**
- **Team consensus: Reframe "Any practitioner" as service-focused (Option 2)**

**Hypothesis:**  
Clearer entry point signaling (visual hierarchy, progressive disclosure, or explicit instruction) could smooth the first moment.

---

### Pattern 4: Role Confusion at Critical Transitions 🆕

**Observed in:**
- **Practitioner registration: Login page immediately after launch**
- **Practitioner registration: "Almost Done" page speaks to multiple audiences**

**Description:**  
At critical handoff moments, the system doesn't acknowledge the user's role or current state. Pages serve multiple audiences (patients, staff, practitioners) without differentiation.

**Examples:**
- After paying and launching practice, login page says: "Existing patients and staff Login to make your next appointment..." (no acknowledgment of practice owner role)
- Post-payment "Almost Done" page offers: "Ready to sign up?" immediately after user just signed up

**Impact:**  
Creates doubt at trust-critical moments: "Am I in the right place? Is this how I'm supposed to log in?" After making a business decision (paying for the service), practice owners need confidence, not role ambiguity.

**Validation Status:** High confidence  
Observed at multiple critical transitions in practitioner flow

**Hypothesis:**  
Context-aware messaging that acknowledges user role ("Welcome to your practice, [Name]") would build confidence at handoff moments.

**Recommendation Priority:** **P1 - High Impact**

---

### Pattern 5: Visual Hierarchy / Cognitive Overload 🆕

**Observed in:**
- **Practitioner dashboard: First login experience**

**Description:**  
The practitioner dashboard presents multiple competing visual elements with no clear priority:
- Yellow "November Updates" button (stale, prominent)
- Large gradient greeting text (28.34px)
- Oversized "January 2026" heading (33.39px)
- Green notification badge
- Multiple navigation options

Meanwhile, the **two most important next steps** (Setup Wizard, Settings) — explicitly called out in the welcome email — have minimal visual prominence.

**Impact:**  
Creates cognitive overload at the moment when clarity matters most. After paying for the service, practice owners need to know: "What do I do first?" Instead, they're scanning through visual noise to find what actually matters.

**Validation Status:** High confidence  
Clear first impression, supported by specific design measurements

**Hypothesis:**  
Visual hierarchy that prioritizes critical next steps (Setup Wizard) over decorative elements would reduce overwhelm and guide practitioners more effectively.

**Recommendation Priority:** **P1 - Medium-High Impact**

---

### Pattern 6: Brand Consistency Erosion 🆕

**Observed in:**
- **Practitioner onboarding: Across 5 different pages**

**Description:**  
The practitioner registration flow spans five pages with inconsistent branding and visual design:

1. **Registration:** HealthFlow logo (top), DynaFlow logo (footer), blue gradient
2. **Payment (Zoho):** DynaFlow logo only, solid blue (no gradient)
3. **Confirmation:** Different teal color scheme (#0A4A53, #046D90)
4. **Login:** No color styling at all (plain white)
5. **Dashboard:** Returns to original blue gradient

**Impact:**  
Visual inconsistency at critical trust moments (payment, launch) can subtly erode confidence. Creates feeling of "lack of cohesion and polish" across onboarding experience.

**Validation Status:** Medium confidence  
Observed systematically across flow, but impact on trust needs validation

**Hypothesis:**  
Unified visual design and consistent brand presence across onboarding would strengthen trust and professionalism.

**Recommendation Priority:** **P2 - Polish / Future Enhancement**

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

### Clarity Moment 3: Welcome Email (Practitioner) ✅ 🆕
**When:** Immediately after practice launch  
**Why it works:** Clear next steps, warm tone, multiple support options, actionable guidance  
**Keep:** This is excellent onboarding via email — could be mirrored in-product

---

## Open Questions

Questions that need more observation to answer:

1. ~~**Does practitioner confusion repeat?**~~ ✅ **ANSWERED**  
   Yes — practitioner flow has similar (and new) confusion patterns

2. ~~**Is system state visibility worse in practitioner onboarding?**~~ ✅ **ANSWERED**  
   Yes — appears at multiple critical transitions (payment, login, dashboard)

3. **Does Setup Wizard address dashboard overwhelm?**  
   - Need to test Setup Wizard flow in next session
   
4. **How do returning users experience these flows?**  
   - Do patterns still hold, or do they only affect first-time users?
   
5. **Mobile vs. desktop?**  
   - Haven't tested mobile yet

6. **Does visual hierarchy issue appear elsewhere?**  
   - Is dashboard unique, or does this pattern appear in other practitioner pages?

---

## Pattern Confidence Levels

| Pattern | Confidence | Evidence | Status |
|---------|-----------|----------|--------|
| **System state visibility** | **CRITICAL - Validated** | **5 observations, both user types** | **Ready for Linear issue** |
| **Practitioner clarity** | **CRITICAL - Validated** | **3 observations, team validated** | **In progress (DYN-13825)** |
| Entry point | Medium | 3 observations | **Linear issue created (DYN-13827)** |
| **Role confusion** | **High** | **2 observations, practitioner-specific** | **Ready for Linear issue** |
| **Visual hierarchy** | **High** | **2 observations (dashboard + contrast with wizard)** | **Ready for Linear issue** |
| Brand consistency | Medium | 1 observation | Needs validation |
| **Good onboarding hidden** | **CRITICAL - Validated** | **2 observations (dashboard vs wizard)** | **Ready for Linear issue (HIGH IMPACT, LOW EFFORT)** |
---

## Next Synthesis Checkpoint

After practitioner Setup Wizard session:
- Test if Setup Wizard addresses dashboard overwhelm
- Validate brand consistency impact
- Decide if Pattern 4-6 are ready for Linear issues
- Consider consolidated "Practitioner Onboarding" Linear issue

---

## Linear Issues Created

**DYN-13825 (High Priority):** Hidden vs. Guided Booking Paths  
**Status:** Team validated, solution in progress

**DYN-13826 (Medium Priority):** Form Completion Soft Enforcement  
**Status:** Team discussion ongoing, multiple action items created

**DYN-13827 (Low Priority):** Entry Point Clarity  
**Status:** Team consensus on Option 2 solution, moving to staging

---

**Notes:**

This is a living document. Early patterns may dissolve. Strong patterns will strengthen. Trust the process.

Practitioner onboarding has revealed that **system state visibility** is a systemic issue, not flow-specific. This elevates its priority significantly.