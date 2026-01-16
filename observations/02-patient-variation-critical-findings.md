# Patient Booking - Variation Pass: Critical Mental Model Breakdown

**Date:** January 6, 2025  
**Session Type:** Variation pass with deep exploration  
**Role:** First-time patient  
**Environments Tested:** Oakland (GQ) and San Francisco (EM)

---

## Critical Discovery: Two Hidden Booking Paths

The system has **two completely different entry paths**, but only teaches one of them explicitly.

### Path 1: "Any Practitioner" (System-Guided)
**Visible instruction:** "Choose a service first then choose a practitioner"

**Actual flow:**
1. Location → Service → Date/Time
2. Practitioner is **inferred** from location (never explicitly chosen)
3. Practitioner name **never appears** in appointment summary
4. User must assume: Oakland = GQ, SF = EM

**Mental model implied:**
"I'm choosing based on service and location. Practitioner doesn't matter or will be assigned."

---

### Path 2: Direct Practitioner Selection (Hidden)
**Visible affordance:** Practitioner images on landing page

**Actual flow:**
1. Click practitioner image directly
2. System auto-selects their location
3. Practitioner **appears** in summary with photo + bio
4. Then: Service → Date/Time

**Mental model implied:**
"I'm choosing based on who I want to see. Location and service follow."

---

## The Problem

**The system doesn't explain there are two paths.**

The visible instruction ("Choose a service first...") **contradicts** the visual affordance (clickable practitioner images).

A first-time user has no way to know:
- That clicking the practitioner image is even possible
- What the difference between these paths is
- Which path matches their intent

---

## Impact on Trust (Healthcare-Specific)

In healthcare, **"who is treating me?"** is a primary trust question.

**Path 1 (Any Practitioner):**
- Practitioner assignment remains invisible throughout flow
- Creates ongoing uncertainty: "Am I seeing GQ? EM? Someone else?"
- Summary never confirms practitioner name
- User must infer from location

**Path 2 (Direct Selection):**
- Practitioner is immediately visible and confirmed
- Creates confidence early
- User knows exactly who they're seeing

**For a real patient**, Path 1 creates trust erosion. Path 2 builds it.

But **Path 2 is hidden**.

---

## Scheduling Logic Discovery

Through experimentation, discovered:

**EM's schedule:**
- Short availability windows (2 hours morning, 2 hours afternoon)
- Cannot accommodate combo bookings (75min acupuncture + 60min massage = 135min total)
- System correctly blocks unavailable slots

**GQ's schedule:**
- Longer availability windows
- Allows combo bookings even at 4:45pm (last slot 5:45pm)
- Either has after-hours buffer OR system allows overbooking (unclear which)

**This scheduling difference is invisible to users** until they try to book and hit "no availability."

---

## Appointment Summary Behavior

### What Updates:
- ✅ Office location (after location selection)
- ✅ Service name + price (after clicking "Continue to select dates")
- ✅ Add-on name + price (after clicking "Continue to select dates")
- ✅ Date & time (after selecting slot or joining waitlist)

### What Doesn't Update (Path 1):
- ❌ Practitioner name (stays "Any practitioner" throughout)
- ❌ Practitioner photo
- ❌ Any indication of who will provide care

### What DOES Update (Path 2):
- ✅ Practitioner photo, name, bio
- ✅ Everything else above

---

## Waiting List Flow

When no slots available:
1. "Add to waiting list" button appears
2. Popup asks for date + time preferences
3. User selects available windows
4. Summary shows: "Date & Time: [DATE] Waiting list"
5. **Does NOT show the specific times selected** (likely intentional - too detailed for summary)

This flow worked as expected. No confusion.

---

## Language/Instruction Issues

### "What kind of service would you like?"
**Context:** Appears AFTER selecting a service  
**Expected:** Confirmation ("You selected...")  
**Actual:** Another question (implies selection not yet made)  
**Impact:** Mild confusion, not blocking

---

## Overall Patterns

### Pattern 1: Mental Model Mismatch (CRITICAL)
The system has two valid booking paradigms but only explains one, and they contradict each other.

**User impact:**
- Path 1 users never know practitioner assignment
- Path 2 capability is discoverable only by accident
- Instructions actively discourage the higher-trust path

### Pattern 2: Scheduling Constraints Hidden
Users can't see practitioner availability windows until they've already chosen service + add-ons.

**User impact:**
- Wasted time selecting combinations that won't fit
- Frustration when "no availability" appears without explanation
- No way to know if it's temporary or systemic

### Pattern 3: Appointment Summary Inconsistency
Summary updates for some selections (service, date) but not others (practitioner in Path 1).

**User impact:**
- Ongoing uncertainty about "who am I seeing?"
- Have to remember/infer information system should confirm

---

## Confidence Impact

**Path 1 (Any Practitioner):**
Would I complete this booking? **Yes, but with reservations.**
- Functional, but requires inference and assumption
- Trust gap around practitioner assignment
- Works for highly motivated patients

**Path 2 (Direct Practitioner Selection):**
Would I complete this booking? **Yes, with confidence.**
- Clear, guided, confirmatory
- Practitioner visible throughout
- Builds trust early and maintains it

**The better path is hidden.**

---

## Recommendations (High-Level)

1. **Make both paths explicit**
   - "Do you have a practitioner in mind? [Yes] [Not yet]"
   - Guide users to the path that matches their intent

2. **Show practitioner in Path 1 summary**
   - After location selection, confirm: "You'll be seeing [Practitioner Name]"
   - Eliminate inference requirement

3. **Surface scheduling constraints earlier**
   - Show practitioner availability windows before service selection
   - OR warn when combinations won't fit before user invests time

4. **Reconcile instruction vs. affordance**
   - Either: Remove practitioner images until after service selection
   - Or: Change instruction to acknowledge both paths exist

---

## Status

**Confidence Level:** VERY HIGH  
**Pattern Validation:** Both paths tested multiple times  
**Ready for:** Linear issue creation, team discussion

---

**This is the highest-impact finding so far.**