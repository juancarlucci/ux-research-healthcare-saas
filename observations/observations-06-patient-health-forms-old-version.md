# Session 06: Patient Health Forms (OLD Version) — Production Testing

**Date:** February 5, 2026  
**Environment:** Lila Production (https://lila.acubliss.app)  
**Test Patient:** Staging Tsting (juancarloscollins+acubliss-staging-patient1@gmail.com)  
**Session Goal:** Document current PHF experience (OLD version) to establish baseline before comparing to staging redesign.

---

## Context

Testing the patient health forms flow on HealthFlow production to understand the current experience. This is the "C grade" version the team referenced in grooming — the baseline we're improving from.

**Entry point:** After account creation, automatically directed to `/portal/forms/personal-info/1/`

---

## Observation 1: Form Complexity & Cognitive Load

### Context
Patient lands on multi-part health history form (6 parts total) after account creation.

### Expectation
Form would guide me through health information collection in manageable chunks, with clear progress and ability to navigate back/forth.

### Reality

**Part 1 (Health Concerns):** 
- ALL diagnostic fields visible at once: Location, Side of pain, Character, Onset, Frequency, Duration, Referral, Aggravating, Relieving
- Clinical language: "Please inform our practitioner of your health concerns"
- Severity slider with unclear label: "There is a range to the severity" (what does this mean?)
- 9+ fields per health concern

**Part 5 (Review of Systems):**
- Massive checkbox list covering multiple body systems
- General, Sleep, Skin/Hair/Nails, Head/Eyes/Ears/Nose/Throat, Respiratory, Cardiovascular, Genito-urinary, Gynecological, Digestive, Musculoskeletal
- Dozens of options per category
- All visible simultaneously on one very long page
- No search, no filtering, no categorization beyond headers

**Part 6 (Additional Health History):**
- More open-ended questions after already comprehensive form

### Impact

**Cognitive overload at critical onboarding moment.** After just creating an account, patients face:
- 6-part form with unclear total time commitment
- Clinical terminology ("Review of systems", "Onset", "Referral")
- Dozens of fields and checkboxes visible at once
- No indication of which fields are required vs. optional

For patients already anxious about health appointments, this creates:
- Decision fatigue (too many choices simultaneously)
- Form abandonment risk (feels too long, too medical)
- Rushed completion (just to get through it)

**Healthcare context matters:** Patients are trying to communicate health concerns, not fill out paperwork. The form structure implies "we need data from you" rather than "help us understand what's bothering you."

### Opportunity

**Direction:** Progressive disclosure + conversational framing.
- Show fewer fields at once (one concern at a time vs. all diagnostic fields)
- Use patient-friendly language ("What brings you in?" vs. "Health concerns")
- Make optional fields truly optional (hide behind "show more" or skip entirely)
- Chunk the "Review of Systems" (expandable categories vs. wall of checkboxes)

---

## Observation 2: Navigation & State Confusion

### Context
User attempts to navigate between form sections using sidebar links and back/continue buttons.

### Expectation
Should be able to move freely between form sections, review previous entries, and submit when ready.

### Reality

**Before submission:**
- Sidebar shows all sections: Personal Information, Notifications, Informed Consent, Patient Health History, Insurance, Other information, etc.
- "Back" button within PHF sections works (Part 2 → Part 1)
- "Back" button does NOT navigate to sidebar links (e.g., from PHF Part 1 to Informed Consent)
- Clicking sidebar links works but loses PHF progress (no "save draft" indication)

**After submission:**
- **CRITICAL:** "This health form has been submitted already and may not be modified"
- Patient Health History disappears from sidebar navigation
- Now tucked under "Completed Forms" (at bottom of sidebar)
- No visual indication this navigation change occurred
- User has no idea where their form went

**Result:** "Where did my form go? Can I edit it? How do I see what I submitted?"

### Impact

**System state visibility gap** (Pattern 1 from synthesis — appears again).

Patients experience uncertainty at multiple handoff points:
1. **During form:** "If I click away, will I lose my work?"
2. **After submission:** "Did it save? Where is it now? Can I update it?"
3. **Trying to find form:** "It was in the sidebar... now it's not... is it gone?"

This is especially problematic in healthcare:
- Patients may remember additional symptoms after initial submission
- They may want to verify what they told the practitioner
- No clear path to review or update

### Opportunity

**Direction:** Make system state explicit.
- Show "Draft saved" indicator during completion
- After submission: "Form submitted! You can view or update it anytime in [link]"
- Keep form accessible in main navigation (don't hide it)
- OR: Allow edits until appointment time (soft lock vs. hard lock)

---

## Observation 3: Language Ambiguity & Unclear Elements

### Context
Throughout form, various labels, instructions, and elements create confusion.

### Expectation
Form language would be clear, patient-friendly, and guide me through completion.

### Reality

**Informed Consent page:**
- Heavy legal language: "Attention: You need to sign a new version of our office policy, informed consent to treatment & HIPAA privacy policy"
- Mysterious text: "jgjguggut" appears in middle of consent (likely placeholder or bug)
- **Can skip without signing** — "Continue" button works even without consent signature
- Undermines importance if optional

**Review of Systems:**
- Medical terminology without explanation
- "Note, this section is very important" — but why? What happens if I skip?
- Unclear which items are truly critical vs. comprehensive

**Completed form summary:**
- "Show" button displays form details
- When details visible, button still says "Show" (should say "Hide" or "Close")
- Creates "did it work?" confusion

**Notifications page loop:**
- After setting notification preferences, clicking "Continue rechecking my information" returns to notifications page (infinite loop)
- Expected: Return to main dashboard or next incomplete section

### Impact

**Small language issues compound into larger trust erosion.**

Each ambiguous element makes patients pause and think:
- "Do I have to sign this or not?"
- "What is 'jgjguggut'?"
- "Did the 'Show' button work?"
- "Why am I back at notifications?"

In healthcare, clarity = trust. Ambiguous language creates:
- Hesitation (is this legitimate software?)
- Errors (skipping important sections thinking they're optional)
- Support burden (patients contacting practice for clarification)

### Opportunity

**Direction:** Audit all patient-facing text.
- Remove placeholder text like "jgjguggut"
- Make required fields truly required (enforce consent signature)
- Improve button labels ("Show" → "Hide" when appropriate)
- Fix navigation loops (notifications → dashboard)
- Use patient-friendly language throughout

---

## Observation 4: Completion Experience & Next Steps

### Context
After completing all 6 parts of PHF, patient sees completion screen.

### Expectation
Clear confirmation of submission with guidance on what happens next.

### Reality

**Completion screen:**
- Green checkmark icon
- "It looks like you're all done! What would you like to do next?"
- Two options:
  - "Go to home page" (primary button)
  - "Continue rechecking my information" (secondary)

**What's good:**
- Visual confirmation (checkmark)
- Friendly tone ("you're all done!")
- Clear CTAs

**What's unclear:**
- No mention of what happens to this information
- No timeline ("Your practitioner will review this before your appointment")
- No way to know if additional forms are required
- "Continue rechecking" button suggests I can edit — but I can't (form is locked)

**Completed form view (after clicking "Show"):**
- Condensed summary format
- Health concern: "back pa - Started:: 10/01/2026, Severity/Pain scale:: #4-5/10, Location:: Low back..."
- Format is practitioner-facing, not patient-friendly
- No edit capability (locked after submission)
- "Show" button doesn't change to "Hide" when content visible

### Impact

**Moment of vulnerability without reassurance.**

Patients have just shared sensitive health information and now wonder:
- "Did the practitioner get this?"
- "When will they see it?"
- "Can I add more details later?"
- "Is this enough information?"

The completion screen misses an opportunity to:
- Set expectations (timeline, next steps)
- Reinforce trust ("Your practitioner will review this carefully")
- Offer support ("Have questions? Contact us")

The locked form creates rigidity — patients can't update even if they remember additional details before appointment.

### Opportunity

**Direction:** Turn completion into confidence-building moment.
- "Submitted! Your practitioner will review this before your appointment."
- "Need to add or update something? You can edit anytime until [appointment date]."
- Clear visual of form status (Submitted ✓, Reviewed, Complete)
- Patient-friendly summary format (not diagnostic shorthand)

---

## Summary: Current PHF Experience (C Grade)

### What Works
- ✅ Comprehensive data collection (practitioners get detailed information)
- ✅ Organized into logical sections (personal info, health history, habits)
- ✅ Functional (technically works, no major bugs beyond navigation quirks)

### Core Problems

**1. Cognitive Overload**
- Too many fields visible at once
- Clinical language ("Review of systems", "Onset", "Referral")
- Massive checkbox lists with no progressive disclosure
- Creates anxiety, not clarity

**2. Navigation Confusion**
- Form disappears from sidebar after submission
- "Back" button doesn't navigate to other sections
- Notification page creates infinite loop
- No "draft saved" indicator

**3. Language Ambiguity**
- Mysterious placeholder text ("jgjguggut")
- Button states unclear ("Show" doesn't change to "Hide")
- Required vs. optional fields ambiguous
- Legal tone instead of supportive tone

**4. Lack of Reassurance**
- Completion screen doesn't set expectations
- Locked form prevents updates
- No visibility into "what happens next"
- Summary format is practitioner-facing, not patient-friendly

### Patient Experience Arc

**Beginning:** "This feels medical and overwhelming"  
**Middle:** "I'm not sure if I'm doing this right"  
**End:** "I hope that was enough information"

**Missing:** Confidence, clarity, support.

---

## Why This Matters (Business Level)

**Patient portal is first impression of practice's digital experience.**

If PHF feels:
- Overwhelming → Patients complete hastily (poor data quality)
- Confusing → Patients contact practice (support burden)
- Clinical → Patients feel processed, not cared for (trust erosion)

The team's goal: Move from C grade (functional but heavy) to B+ grade (clear and supportive) to A grade (conversational and intelligent).

**This observation documents the C grade baseline** so we can measure improvement against it.

---

## Next Steps

1. **Test NEW PHF redesign on staging** (once access granted)
2. **Compare old vs. new experience** (document improvements)
3. **Identify remaining gaps** (B+ → A grade path)
4. **Consider conversational AI approach** (team's A grade vision)

---

## Session Notes

**Energy check:** Illuminating — seeing the current experience helps contextualize the team's redesign decisions. The "C grade" assessment is accurate.

**Surprising moments:**
- How much clinical terminology pervades patient-facing text
- The navigation confusion after form submission (where did it go?)
- The "jgjguggut" placeholder text (quality control gap)

**Follow-up questions:**
- Can patients edit forms after submission? (Should they be able to?)
- What happens if they abandon mid-completion? (Draft saving?)
- How do practitioners actually use this data? (Format implications)

**Related patterns:**
- **Pattern 1 (System State Visibility):** Confirmed again — form disappears after submission with no clear indication
- **Pattern 5 (Visual Hierarchy):** Too many elements competing for attention (all fields visible at once)
- New pattern emerging: **Clinical Language Barrier** — practitioner-oriented terminology throughout patient experience
