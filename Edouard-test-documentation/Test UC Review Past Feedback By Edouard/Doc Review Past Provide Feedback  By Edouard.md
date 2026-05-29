# TEST NOTES — Review Past Feedback (Student Role)

---

## What I am testing

I am testing:

> Student access to previously completed surveys and submitted feedback history (“Review Past Feedback” use case)

The objective is to verify:

* access to completed surveys
* visibility of historical responses
* data persistence
* role-based access restrictions
* usability of feedback history navigation

---

## What I did (steps)

1. Logged into the application as Student
2. Opened the dashboard
3. Accessed the “My Completed Surveys” menu
4. Opened previously submitted surveys
5. Reviewed displayed questions and responses
6. Refreshed the page after viewing responses
7. Logged out and logged back in
8. Checked whether completed surveys remained accessible
9. Attempted to identify search/filter features
10. Verified whether access to other students’ surveys was possible

---

## What I noticed

* “My Completed Surveys” is available after authentication
* Completed surveys are displayed in a list format
* Only survey titles are visible in the list view
* Clicking a survey displays submitted questions and answers
* Survey details are displayed directly below the survey list
* Historical data remains accessible after refresh and session restart
* Students can only access their own completed surveys
* No search functionality exists
* No filtering system exists
* No export functionality is available for Student role

---

## What should have happened

Based on the documented use case:

* Survey history should display:

  * title
  * submission date
  * completion status
* Students should be able to search or filter historical surveys
* Historical survey navigation should remain readable and structured
* Role restrictions should prevent access to other students’ data

---

## Is this a problem?

Yes

---

## Summary of issues

### 1. Missing survey metadata in history view

**Observed behavior:**

* Only survey titles are displayed
* No submission date shown
* No completion status shown

**Impact:**
Reduces historical traceability and context visibility.

**Type:**
UI / Missing Information

**Severity:**
Medium 🟡

---

### 2. Missing search and filtering functionality

**Observed behavior:**

* No search bar exists
* No filtering by date or survey title exists

**Impact:**
Makes navigation difficult when many completed surveys exist.

**Type:**
UX / Missing Behavior

**Severity:**
Medium 🟡

---

### 3. Inline display of survey details reduces readability

**Observed behavior:**

* Detailed responses appear directly beneath the survey list instead of opening in a dedicated page or modal

**Impact:**
Weak separation between navigation and detailed content.

**Type:**
UX / Interface Design

**Severity:**
Low 🟢

---

## Special notes

* Authentication-based access control works correctly
* Students cannot access surveys belonging to other users
* Historical responses persist correctly across sessions
* Completed surveys remain accessible after refresh
* Export functionality is correctly unavailable for Student role

These areas are compliant with the expected use case behavior.

---

## Evidence

Observed during live testing through:

* completed survey navigation
* session persistence testing
* refresh testing
* access restriction verification

Screenshots captured during:

* “My Completed Surveys” navigation
* response detail visualization
* history persistence checks

---

## My thoughts / questions

* Should survey history support long-term navigation with filters?
* Should response details open in a dedicated page instead of inline expansion?
* Is metadata intentionally omitted or not yet implemented?
* Will future versions include export/search functionality for students?

---

## Action taken

* Documented missing historical navigation features
* Verified access control behavior
* Continued persistence and usability testing

---

## Conclusion

The system provides a stable and secure implementation of the Student feedback history workflow. Core functionalities such as authentication, response retrieval, and session persistence behave correctly.

However, the history management experience remains incomplete due to:

* missing metadata
* absence of search/filter capabilities
* limited readability of detailed response visualization

From a QA perspective, the system is:

* functionally stable
* secure at access-control level
* but incomplete regarding historical usability features

---
