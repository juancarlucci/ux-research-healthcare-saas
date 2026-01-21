# Practitioner Setup Wizazrd - First pass
---

## Session Info

**Date:** January 15, 2026  
**Duration:** ~90 minutes  
**Role:** First-time practice owner (continuing from registration)  
**Scenario:** Exploring Setup Wizard to configure practice for first time  
**Environment:** Production (jc-test-acupuncture.healthflow.app)

---

## Session Goals
What are you specifically testing/observing?

- Test if Setup Wizard addresses dashboard orientation gap
- Observe configuration flow (what's required, what's guided)
- Document friction points in practice setup
- Compare to dashboard's visual hierarchy issues

---

## Raw Notes

### Initial Impression

**Visual Design:**
- Clean, white background with black text
- Different styling from dashboard (simpler, clearer)
- HealthFlow logo in blue on left sidebar
- 6-step structure clearly visible

**First feeling:** Looks good, simple, well-structured

**Structure:**
- Left sidebar shows 6 steps with labels
- Step 1 currently highlighted
- Main content area shows current step details

---

### Step 1: Practice & Offices

**Guidance provided:**
"This is a one time set up wizard. After completion, you may change settings from the individual settings pages themselves.

Services are required for scheduling patients. Consider naming them so patients may choose the correct one in the patient portal. Services are NOT CPT codes. An example would be 'Followup Treatment'. Give them prices in 'Service Pricing,' chose what practitioners offer them in 'Service rules' and, whether patients can see them in the patient portal within the 'Control center.'"

**Form fields:**
- Practice name (pre-filled: JC-test-Acupuncture)
- Practice email
- Practice website
- Office details (name, address, number of rooms, etc.)

**Helpful features:**
- Info boxes: "Want to manage resources like reclining chairs for community acupuncture? Do this on the office settings page after done with the wizard."
- "Add another office" button (expands new form)
- Pre-filled data carried over from registration

**Experience:** Straightforward, made sense, no friction

**URL when office added:** https://jc-test-acupuncture.healthflow.app/practice/settings/offices/

---

### Step 2: Services

**FRICTION POINT 1: Field Validation Failure**

**What happened:**
- Abbreviated name field has 10-character limit
- Entered "follow-up-acu" (13 characters)
- Field turned from red to blue when I shortened by one character
- Blue = looks valid
- But still over 10 characters
- Only discovered error when clicking "Save and continue"

**Expected:** Real-time validation with character counter showing "9/10 characters"

**Impact:** False positive feedback — blue suggests valid when it's not

---

**FRICTION POINT 2: "Back" Button Breaks Wizard Flow**

**What happened:**
1. Saved Step 2 (Services)
2. Clicked "Back" button to review what I entered
3. Got modal: "You have already added services to your practice. Go to services settings page to continue editing. Exit set up wizard"

**Only two options:**
- "Exit set up wizard" → Takes to dashboard (https://jc-test-acupuncture.healthflow.app/practice/dashboard/)
- "Go to services settings page to continue editing" → Takes to services settings (https://jc-test-acupuncture.healthflow.app/practice/settings/services/)

**NO option to continue wizard**

**Main content blurred out**, cannot be accessed

**Expected:** Be able to review previous steps without exiting wizard, or at minimum continue from Step 3

**Impact:** Creates confusion — "Did I break something? Can I finish the wizard?"

---

**DISCOVERY: Sidebar Steps Still Clickable**

Even though Steps 1-2 were blurred in the modal, **Steps 3-6 were NOT blurred** and remained active.

Clicked Step 3 → Was able to continue the wizard

**This is confusing:**
- Modal says "Exit wizard" (implies can't continue)
- But CAN continue by clicking sidebar
- Not obvious, easy to miss

---

**Services Settings Page Experience:**

After forced exit, landed on Services settings page:

**Two communications at top:**
1. Same guidance from wizard about services and CPT codes
2. "Packages! Note: Do not create packages here! Creating your services first and then [follow this article] to learn how to create and sell your packages."

**Clicked "learn how to create..." link:**
- Brief popup: "Hi Juan How can we help?"
- Then second popup: "Packages" with long detailed content
  - Table of contents: Overview, Setting up packages, Charging them for a package, Return Visits
- Took quick look, closed it (not relevant right now)

**FRICTION POINT 3: "No category" Confusion**

Large font text at top of services section: "No category"

**Questions:**
- What are category choices?
- How do I create a category?
- Where do categories show up?
- How to edit?
- Is this required?

**"No category" is not clickable, no guidance provided**

**Helpful elements:**
- "?" popup icon (helpful)
- "Watch Video" button (helpful)
- Each service assigned a color for visual distinction

---

### Step 3: Staff

**Resumed wizard by clicking Step 3 in sidebar**

**Staff Roles Hierarchy — Complex but Discoverable:**

**Practice Owner (Me):**
- ❌ Front Office (greyed out, cannot enable)
- ✅ Manager (checked, greyed out)
- ✅ Administrator (toggleable — acts as master switch)
- ✅ Practitioner (checked, greyed out, cannot disable)
- ✅ Biller (toggleable when Admin is off)
- ✅ Inventory (toggleable when Admin is off)

**Logic discovered:**
- **Practitioner role = permanent** (I'm an acupuncturist, can't remove this)
- **Admin = master switch** — when on, unlocks Manager, Biller, Inventory
- **Front Office = staff-only role** (practice owner can't be front office?)

**Additional Practitioner (Dr. Pat):**
- Default: Only Practitioner checked
- Can enable: Admin, Manager, Biller, Inventory
- All roles toggleable

**Staff (non-practitioner - Bert):**
- Cannot be: Practitioner or Admin
- Can be: Front Office, Manager, Biller, Inventory

**Helpful warning:**
"I acknowledge that after the 15 day trial is over, I will be charged $25.00/month for each additional practitioner."

This **disables the "Save and continue" button** until acknowledged.

**Overall feeling:** Had questions, but mostly easy to figure out. Logic made sense once I experimented.

**Email notifications received:**
- "New staff account created for Dr. Pat the Practitioner, DAM on 01/19/2026"
- "New staff account created for Bert staff person Staffing on 01/19/2026"
- Both emails professional, included link to visit practice

---

### Step 4: Schedule — Straightforward

**Fields provided:**
- Limit online booking openings per day
- Gap preference in schedule (prefer appointments next to existing vs. scattered)
- Overlapping appointment handling (allow/prefer/make less available)
- Custom messages for patient notifications (new appointment, 1st reminder, 2nd reminder)
- Insurance questions toggle (yes/no)
- Timing for email reminders (1st and 2nd)
- Timing for SMS reminders (1st and 2nd)

**Experience:** Clear options, understandable fields, no friction

---

### Step 5: My Work Hours — Clear

**Helpful guidance:**
"Please note that you're setting up your own work hours, you can set up another practitioner's work hours later on the schedule"

**Fields for each day of week:**
- Start time
- End time
- Office (dropdown: San Francisco, test-2-office)
- Repeat (every week, every other week, every month)
- Services (checkboxes for services created in Step 2):
  - test-follow-up acupuncture session
  - test-initial-acupuncture session
  - test 50 min massage session

**Experience:** Self-explanatory, intuitive, no friction

---

### Step 6: Activating Product Vendors

**Guidance:**
"HealthFlow has many of your favorite herbal and supplement vendors with all of their products 'baked' into the software, allowing you to initialize inventory and most importantly, prescribe products with ease. Activate only the vendors who's products you intend to prescribe or carry, and once you have done so, you may further edit and create purchase orders and more outside of the wizard."

**For each vendor:**
- Company name (e.g., "Evergreen Herbs & Medical Supplies LLC")
- Type (vendor and manufacturer)
- Default mark-up % (with option to apply to all products)
- Tax settings (use office tax rate?)
- Allow partial sale of herbal granules? (Yes/No)
- Require practitioner recommendation to sell products? (Yes/No)
- "Complete Activation" button per vendor

**Experience:** Detailed but clear, no friction

---

### Completion Screen — Good Next Steps

**Message:** "Looks like we're all set up! You are ready to start booking patients, you can continue to configure your practice."

**Five clear next action buttons:**
1. **"Configure your practice's policies"** (highlighted in blue - primary CTA)
2. "Import patient data"
3. "Configure schedule options"
4. "Configure service rules"
5. "Go to help page"

**Links:**
- https://jc-test-acupuncture.healthflow.app/practice/settings/policies/
- https://jc-test-acupuncture.healthflow.app/practice/settings/import/
- https://jc-test-acupuncture.healthflow.app/practice/settings/schedule/
- https://jc-test-acupuncture.healthflow.app/practice/settings/service-rules/
- https://help.healthflow.app/en/

**Experience:** Well-designed transition, clear direction without overwhelming

---

## Structured Observations

### Observation 1: Setup Wizard Provides Structure Dashboard Lacks

**Context:**  
As a first-time practice owner, after experiencing the overwhelming dashboard (multiple competing visual elements, unclear priorities), I entered the Setup Wizard to configure my practice.

**Expectation:**  
I expected guidance on "what to do first" and step-by-step structure for practice configuration.

**Reality:**  
The Setup Wizard provides exactly this:
- Clear 6-step sequential structure
- One focus area at a time
- Helpful contextual guidance at each step
- Pre-filled data from registration
- Clean, simple visual design
- Manageable complexity

Steps 3-6 (Staff, Schedule, Work Hours, Product Vendors) were all straightforward with clear fields and appropriate guidance.

**Impact:**  
The Setup Wizard **solves the dashboard orientation problem.** After paying for the service and facing a cluttered dashboard, the wizard provides the clarity and confidence a practice owner needs. It answers: "What do I need to do to get my practice running?"

This is a **strength** of the product. The completion screen offers clear next steps without overwhelming.

**Opportunity:**  
Consider making the Setup Wizard the **default landing experience** after first login, rather than the dashboard. The welcome email already says "Start with the Setup Wizard" — making this the automatic first experience would eliminate the dashboard overwhelm entirely for new practice owners.

---

### Observation 2: Field Validation Provides False Positive Feedback

**Context:**  
In Step 2 (Services), while entering an abbreviated name for a service.

**Expectation:**  
Real-time feedback on field validity, especially for character limits.

**Reality:**  
- Abbreviated name field has 10-character limit (not visible)
- Entered "follow-up-acu" (13 characters) — field showed red
- Shortened by one character to "follow-up-ac" (12 characters)
- Field turned blue (visual signal of validity)
- But still over 10-character limit
- Only discovered error when clicking "Save and continue"

**Impact:**  
Blue color signals "valid" when field is still invalid. Creates frustration: "I fixed it, why is it still erroring?" Requires trial-and-error to discover the actual 10-character limit.

**Opportunity:**  
Add real-time character counter (e.g., "9/10 characters") and maintain red/blue feedback accuracy. Show limit visibly before user enters data.

---

### Observation 3: "Back" Button Creates Wizard Exit Confusion

**Context:**  
In Step 2 (Services), after saving services and moving forward, I clicked "Back" to review what I had entered.

**Expectation:**  
Be able to review previous step without exiting the wizard.

**Reality:**  
Clicking "Back" triggered a modal: "You have already added services to your practice. Go to services settings page to continue editing. Exit set up wizard"

Only two options provided:
- Exit wizard (go to dashboard)
- Go to services settings page

Main content blurred and inaccessible. No option to continue wizard from Step 3.

**However:** Steps 3-6 in the sidebar remained clickable (though 1-2 were blurred). Clicking Step 3 allowed me to continue the wizard.

**Impact:**  
Creates confusion at a critical moment: "Did I break something? Can I still finish setup?" The modal language ("Exit wizard") implies you cannot continue, but you actually can via the sidebar — this is not obvious.

For a first-time practice owner trying to ensure everything is configured correctly, this creates unnecessary doubt.

**Opportunity:**  
Either: (1) Allow "Back" navigation without triggering exit, or (2) Make it clear in the modal that you can continue the wizard by clicking the next step in the sidebar, or (3) Add a third option: "Continue to Step 3" in the modal.

The sidebar being clickable is good — it just needs to be more discoverable when the modal appears.

---

### Observation 4: "No category" Label Lacks Context

**Context:**  
In the Services settings page (reached after forced exit from wizard Step 2).

**Expectation:**  
Clear understanding of what "categories" are and how to use them.

**Reality:**  
Large header text says "No category" at the top of the services section. It's not clickable, has no explanation, and provides no guidance on:
- What categories are
- How to create one
- Where they appear
- Whether they're required or optional

**Impact:**  
Creates low-level uncertainty: "Should I have a category? Am I missing something?" Not blocking, but adds to cognitive load during initial setup.

**Opportunity:**  
Add contextual help (tooltip or info icon) explaining: "Categories help organize your services for easier management. They're optional. [Learn more]"

---

## Quick Synthesis (End of Session)

### What repeated from previous sessions?

**System state visibility gap** — Even in the well-structured wizard, moments of uncertainty arose:
- Field validation didn't clearly communicate limits
- "Back" button behavior wasn't explained
- "No category" lacked context

However, the wizard **significantly reduces** this pattern compared to dashboard and registration flow.

### What's new/different this time?

**Setup Wizard is a STRENGTH:**
- Clear sequential structure
- Helpful guidance at each step
- Manageable complexity
- Good completion experience

**This addresses the dashboard overwhelm issue** — the wizard provides exactly the orientation new practice owners need.

**Staff role hierarchy** was complex but discoverable through experimentation.

**Email notifications** work well — received confirmations for staff additions.

### Biggest takeaway (one sentence):

The Setup Wizard demonstrates that HealthFlow **knows how to create good onboarding experiences** — making it the default first experience (instead of starting at the cluttered dashboard) would significantly improve practitioner confidence and reduce setup friction.

---

## Follow-up Actions

- [x] Complete session log with structured observations
- [ ] Create Linear issue: Field validation improvement (Step 2)
- [ ] Create Linear issue: "Back" button UX in wizard
- [ ] Consider Linear issue: Make Setup Wizard default landing for new practitioners
- [ ] Update patterns.md with wizard findings

---

## Energy Check

How did this session feel?
- [x] Energizing — learned a lot
- [ ] Neutral — productive but unremarkable  
- [ ] Draining — too long or repetitive

**Note for next time:**
Session was ~90 minutes (Setup Wizard Steps 1-6 complete). Felt productive — discovered that the wizard is actually well-designed and solves the dashboard problem. The friction points (validation, back button, "no category") are fixable polish issues, not fundamental flaws. 

Key insight: The product has good onboarding DNA (the wizard), it's just hidden behind a confusing entry point (dashboard).

Next session could focus on: Testing "Configure policies" or other post-wizard settings to see if the good structure continues.