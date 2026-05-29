# TEST NOTES — Provide Feedback (Survey Completion)

---

## What I am testing

I am testing:

> Student survey completion workflow (“Provide Feedback” use case)

The objective is to verify:

* survey accessibility
* question handling
* validation behavior
* response persistence
* submission workflow
* compliance with the documented use case

---

## What I did (steps)

1. Logged into the application as Student
2. Opened the dashboard
3. Accessed available surveys from the navigation menu
4. Opened multiple surveys containing:

   * text questions
   * multiple choice questions
   * rating-based questions
5. Started answering survey questions
6. Navigated between survey sections
7. Refreshed the page before submission
8. Logged out during completion
9. Reopened the survey after interruption
10. Attempted final submission
11. Checked completed survey behavior after submission

---

## What I noticed

* Surveys are accessible only after authentication
* Surveys are displayed through categorized sections instead of one continuous form
* Required fields are enforced before submission
* Submission confirmation is displayed successfully
* Completed surveys become read-only after submission
* Refreshing the page removes unsaved responses
* Logging out during completion causes total progress loss
* No autosave mechanism exists
* No “resume incomplete survey” functionality exists
* No notification or indicator exists for unfinished surveys

---

## What should have happened

Based on the documented use case:

* Survey progress should be automatically saved during completion
* Users should be able to resume incomplete surveys after interruption
* Partial responses should persist after refresh or logout
* The system should indicate unfinished surveys to the student
* Navigation between questions should support a continuous completion workflow

---

## Is this a problem?

Yes

---

## Summary of issues

### 1. Missing autosave mechanism

Survey progress is not persisted during completion.

**Observed behavior:**

* Refresh removes all unsaved data
* Leaving the page resets progress

**Impact:**
High risk of data loss during survey completion.

**Type:**
Functional / Data Persistence

**Severity:**
High

---

### 2. No resume capability for incomplete surveys

**Observed behavior:**

* Interrupted surveys restart from the beginning
* No partial state restoration exists

**Impact:**
Breaks continuity of user workflow.

**Type:**
Workflow / UX

**Severity:**
High

---

### 3. Missing incomplete survey notification

**Observed behavior:**

* No visual indicator for unfinished surveys
* No reminder or pending status shown

**Impact:**
Reduces usability and workflow visibility.

**Type:**
UX / Missing Behavior

**Severity:**
Medium

---

### 4. Section-based navigation differs from expected linear workflow

**Observed behavior:**

* Surveys are split into sections with separate access links

**Impact:**
Partial divergence from the expected survey completion flow described in the use case.

**Type:**
UX / Workflow Design

**Severity:**
Low

---

## Special notes

* Validation of required fields is correctly enforced
* Duplicate submissions appear prevented
* Completed surveys cannot be modified afterward
* Submission confirmation workflow functions correctly

These areas are compliant with the expected use case behavior.

---

## Evidence

Observed during live testing through:

* dashboard navigation
* survey completion workflow
* refresh/logout interruption tests
* post-submission verification

Screenshots captured during:

* survey access
* validation testing
* submission workflow
* interruption scenarios

---

## My thoughts / questions

* Should incomplete surveys be stored automatically after each question?
* Is section-based navigation intentionally replacing a continuous survey flow?
* Should interrupted sessions generate a recovery mechanism?
* Is temporary response persistence planned in future iterations?

---

## Action taken

* Documented inconsistencies during live testing
* Identified missing persistence features
* Continued workflow testing across multiple survey scenarios

---

## Conclusion

The system correctly implements the final survey submission workflow and validation constraints. However, important lifecycle management features expected by the use case are missing.

The most significant gaps are:

* absence of autosave
* lack of interruption recovery
* absence of incomplete survey persistence

These issues directly impact usability, workflow continuity, and data reliability during survey completion.

---
