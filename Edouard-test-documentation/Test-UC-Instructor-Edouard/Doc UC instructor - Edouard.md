## UC-INSTRUCTOR QA TEST REPORT — SURVEY MANAGEMENT SYSTEM

---

# 1. Context and Objective

This report documents the testing of the Instructor survey management workflow within the system, based on the following use cases:

* UC-Manage Survey
* UC-Manage Question Type
* UC-Provide Feedback (Student)
* UC-Review Past Feedback

The objective was to evaluate:

* survey creation and lifecycle
* question management
* student response workflow
* data consistency across roles (student/instructor)
* system behavior under modification and deletion scenarios

Testing was performed using multiple student accounts and one instructor account.

---

# 2. Scope of Testing

## 2.1 Instructor Functional Areas

* Survey creation
* Survey editing
* Survey deletion and restoration
* Question creation and association
* Survey publication
* Response monitoring

## 2.2 Student Functional Areas

* Survey access
* Response submission
* Response persistence
* Completed survey history

## 2.3 Data Flow Validation

* Survey → Questions → Student Responses → Instructor View

---

# 3. Test Execution Summary

## 3.1 Survey and Question Management

* Surveys were successfully created and published.
* Questions were created and linked to surveys.
* Multiple question types were tested (text, multiple choice, true/false).

## 3.2 Student Workflow

* Students were able to:

  * access surveys
  * submit responses
  * view completed surveys
* Responses were correctly stored and displayed in the instructor interface.

## 3.3 Instructor Responses

* Survey responses were accessible in real time.
* Data between student submissions and instructor view was generally synchronized.

---

# 4. Observed Inconsistencies

## 4.1 Inconsistency in Validation Behavior

The system allows publication of surveys and questions even when mandatory fields are empty.

* Surveys without titles are accepted.
* Questions without content are accepted.

This creates structural inconsistencies in survey definitions.

---

## 4.2 Inconsistency in Response Persistence

Student responses are not preserved when the page is refreshed or when the survey is left before submission.

* All unsaved data is lost.
* No recovery mechanism is available for incomplete submissions.

This leads to inconsistencies in expected user progress behavior.

---

## 4.3 Inconsistency in Historical Question Handling

After deletion of a question:

* Student completed survey view no longer displays the question.
* Instructor response history still retains the associated data.

This creates a mismatch between student and instructor historical views.

---

## 4.4 Inconsistency in Survey Deletion Behavior

After survey deletion:

* The survey disappears from the instructor survey list.
* Student completed history still retains the survey entry.

This results in divergent states between user roles.

---

## 4.5 Inconsistency in Preview Access

Instructor preview functionality does not provide a student-like view.

* Preview access is restricted.
* No simulation mode is available.

This limits validation of the final student experience.

---

# 5. Compliance with Use Cases

## Functional Areas Working Correctly

* Survey creation ✔
* Question management ✔
* Student submission ✔
* Role-based access control ✔
* Response storage ✔

## Areas Showing Deviations

* Validation of mandatory fields
* Persistence of incomplete student responses
* Consistency of historical data across roles
* Preview experience for instructors

---

# 6. Conclusion

The system provides a functional end-to-end survey workflow, covering creation, response collection, and result visualization.

However, several inconsistencies are observed in:

* validation enforcement
* data persistence behavior
* historical data alignment between roles
* preview experience limitations

### Key recommendation:

Harmonize validation rules and unify data persistence logic across student and instructor modules to ensure consistent behavior throughout the survey lifecycle.
