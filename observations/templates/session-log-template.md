# Session Log Template

Use this for quick capture during or immediately after a testing session. Raw notes that you'll later synthesize into structured observations.

---

## Session Info

**Date:** January 14, 2026  
**Duration:** [fill in after]  
**Role:** First-time practice owner (continuing from registration)  
**Scenario:** Exploring Setup Wizard to configure practice for first time  
**Environment:** Production (jc-test-acupuncture.acubliss.app)

## Session Goals
- Test if Setup Wizard addresses dashboard orientation gap
- Observe configuration flow (what's required, what's guided)
- Document friction points in practice setup
- Compare to dashboard's visual hierarchy issues

---

### Setup Wizard — Steps 1-2

**STRENGTHS:**
- Clear 6-step structure in sidebar
- Helpful contextual info boxes
- Pre-filled data from registration
- Cleaner visual design than dashboard
- Help resources (?, Watch video)

**FRICTION POINT 1: Field Validation**
- Abbreviated name has 10-char limit
- Field turns blue even when over limit
- Error only shows on save attempt
- Need: Real-time validation + character counter

**FRICTION POINT 2: Wizard "Back" Button Breaks Flow**
- After saving Step 2 (Services), clicked "Back" to review
- Got message: "You have already added services... Exit wizard"
- Only options: Exit wizard OR go to settings page
- NO option to continue wizard
- Expected: Be able to review previous steps without exiting

**FRICTION POINT 3: Forced Exit Creates Confusion**
- Forced to exit wizard at Step 2
- Now on Services settings page
- Uncertain: "Did I finish the wizard? What steps remain? How do I resume?"

**FRICTION POINT 4: "No category" Header**
- Large text "No category" at top of services section
- Not clickable, no explanation
- Questions: "What are categories? How to create? Are they required?"

---

### Setup Wizard — Steps 3-6 (Resumed via Sidebar)

**DISCOVERY: Wizard can be resumed from sidebar**
- After "exit wizard" modal, Steps 3-6 still clickable in sidebar
- Not obvious — modal implies you must exit
- Could continue wizard by clicking Step 3

**Step 3: Staff — Complex but Discoverable**
- Practice owner roles: Manager/Admin/Practitioner (some locked)
- Admin = master switch (unlocks Biller, Inventory)
- Practitioner role = permanent (can't be removed)
- Front Office greyed out for practice owner
- Additional practitioner: All roles toggleable except Front Office
- Staff (non-practitioner): Can't be Practitioner or Admin
- Helpful warning: "$25/month charge for additional practitioners"
- Overall: Had questions but could figure it out

**Step 4: Schedule — Straightforward**
- Clear options for online booking, gaps, overlapping appointments
- Notification customization (email + SMS reminders)
- Insurance questions toggle
- No friction

**Step 5: Work Hours — Clear**
- Helpful note: "Setting YOUR hours, can set others later"
- Start/end time, office, repeat pattern, services
- Intuitive

**Step 6: Product Vendors — Detailed but Clear**
- Activate vendors one-by-one
- Markup, tax, partial sales, practitioner rec settings
- "Complete Activation" button per vendor
- No friction

**Completion Screen — Good Next Steps**
- "Looks like we're all set up!"
- 5 clear next actions (policies, import data, schedule, service rules, help)
- Configure policies highlighted (primary CTA)
- Well-designed transition
---

## Follow-up Actions

- [ ] Turn observation X into structured format
- [ ] Screenshot/record moment Y
- [ ] Ask JL/GQ about Z
- [ ] Add to patterns.md

---

## Energy Check

How did this session feel?
- [ ] Energizing — learned a lot
- [ ] Neutral — productive but unremarkable  
- [ ] Draining — too long or repetitive

**Note for next time:**