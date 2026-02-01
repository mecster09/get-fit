# User Stories — Weight Loss Tracker

## Persona
**App User**

---

## Epic 1 — Profile & Configuration

### US-01: Create / edit my profile
As an App User, I want to enter and update my personal details (sex, age, current weight, target weight) so the app can personalize my plan and calculate progress metrics.

**Acceptance Criteria (BDD)**
- Given I open the Config section  
  When I enter Sex, Age, Current Weight, and Target Weight and save  
  Then the values persist and are shown when I return to Config.
- Given I have saved values  
  When I update any field and save  
  Then the updated values persist and the dashboard recalculates using the new data.
- Given I enter invalid inputs  
  When I try to save  
  Then validation errors are shown and saving is blocked.

---

## Epic 2 — Fasting Schedule Configuration

### US-02: Set a repeating weekly fasting/eating window
As an App User, I want to define a weekly fasting/eating schedule so the app can show what I should do today and this week.

**Acceptance Criteria**
- Given I am in Config → Fasting  
  When I set a repeating schedule for all days and save  
  Then the schedule persists and appears in Today and This Week.

### US-03: Add an exception day to my fasting schedule
As an App User, I want to set exception days so my plan matches real-life variation.

**Acceptance Criteria**
- Given a repeating schedule  
  When I override a specific day  
  Then only that day uses the exception schedule.
- Given an exception exists  
  When I remove it  
  Then the day reverts to the repeating schedule.

---

## Epic 3 — Exercise Schedule Configuration

### US-04: Configure treadmill minutes
As an App User, I want to schedule treadmill exercise minutes on specific days.

**Acceptance Criteria**
- Given I select days and set treadmill minutes  
  When I save  
  Then the weekly schedule appears in Today and This Week.
- Given minutes are removed or set to zero  
  Then the exercise is no longer scheduled for that day.

---

## Epic 4 — Resistance Training Schedule Configuration

### US-05: Configure resistance training sessions
As an App User, I want to plan resistance training by sets, exercises, and reps on specific days.

**Acceptance Criteria**
- Given I define sets, exercises per set, and reps  
  When I save  
  Then the resistance plan summary is shown for that day.
- Given invalid inputs  
  When I try to save  
  Then validation errors are shown.

---

## Epic 5 — Schedule Views

### US-06: View Today
As an App User, I want to see today’s fasting, exercise, and resistance plan.

**Acceptance Criteria**
- Given schedules exist  
  When I open Today  
  Then today’s plan is clearly displayed.
- Given no plan exists  
  Then the activity shows as not scheduled.

### US-07: View This Week
As an App User, I want to see a full weekly breakdown of my plan.

**Acceptance Criteria**
- Given schedules exist  
  When I open This Week  
  Then a 7-day breakdown is shown.
- Given fasting exceptions  
  Then those days reflect the exception schedule.

---

## Epic 6 — Progress Dashboard

### US-08: View progress to target weight
As an App User, I want to see progress toward my target weight.

### US-09: View current BMI
As an App User, I want to see my BMI calculated using industry-standard formulas.

### US-10: View trend and estimated timeline
As an App User, I want to see my weight-loss trend and an estimated timeline to reach my target.

---

## Optional

### US-11: Record weight over time
As an App User, I want to log my weight so trends and projections can be calculated.
