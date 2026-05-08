# TEST REPORT — PROVIDE FEEDBACK (SURVEY COMPLETION)

## 1. Introduction

This document presents the results of functional and behavioral testing performed on the **“Provide Feedback”** use case within the Student Survey Application.

The objective is to verify whether the system correctly supports:
- survey access
- survey completion
- data persistence
- validation rules
- submission workflow
- compliance with the specified Use Case requirements

---

## 2. Use Case Reference

### Core Requirements

The system must allow a Student to:

- access available surveys after authentication
- complete surveys containing multiple question types:
  - multiple choice
  - rating scales
  - open-ended questions
- navigate between questions
- save progress automatically during completion
- resume incomplete surveys after interruption
- submit completed surveys successfully
- receive a confirmation message after submission

---

## 3. Observed System Behavior Overview

The system behavior was analyzed during multiple test scenarios. The following global behavior was observed:

- Surveys are accessible after login via dashboard navigation
- Surveys are structured into sections (not a single continuous form)
- Submission is possible only when all required fields are completed
- Confirmation message is displayed after successful submission
- Completed surveys are locked and cannot be modified

---

## 4. Functional Analysis (Use Case vs Implementation)

| Requirement | Observed Behavior | Status |
|--------------|------------------|--------|
| Survey access after login | Available via dashboard | ✅ Compliant |
| Survey listing | Available with categorized sections | ⚠️ Partial divergence |
| Question types support | Functional (MCQ, text, ratings) | ✅ Compliant |
| Navigation between questions | Limited (section-based navigation) | ⚠️ Partial |
| Required field validation | Enforced before submission | ✅ Compliant |
| Autosave of progress | Not implemented | ❌ Not compliant |
| Resume incomplete survey | Not implemented | ❌ Not compliant |
| Progress persistence | Not implemented | ❌ Not compliant |
| Submission confirmation | Displayed successfully | ✅ Compliant |
| Post-submission immutability | Correctly enforced | ✅ Compliant |
| Notification of incomplete surveys | Not implemented | ❌ Not compliant |

---

## 5. Key Functional Issues Identified

### 🔴 1. No Autosave Mechanism

The system does not persist user input during survey completion.

- Refreshing the page results in complete data loss
- Navigating away resets the survey state
- No intermediate storage is performed

**Impact:** Critical data loss risk during user interaction

---

### 🔴 2. Loss of Survey Progress After Interruption

Survey responses are not retained after:
- page refresh
- logout
- browser closure

**Impact:** Users must restart surveys from the beginning

---

### 🔴 3. No Resume Capability for Incomplete Surveys

The system does not allow continuation of partially completed surveys.

- No saved state is restored
- No "continue survey" option exists
- Survey is treated as new on each access

**Impact:** Breaks continuity of user workflow

---

### 🔴 4. No Notification for Incomplete Surveys

Users are not informed of:
- pending surveys in progress
- unfinished submissions

**Impact:** Reduced visibility and poor user guidance

---

### ⚠️ 5. Section-Based Survey Structure

Surveys are not presented as a continuous form but as:
- grouped sections with separate links

**Impact:** Divergence from expected linear survey flow defined in the Use Case

---

## 6. Security and Data Integrity Observations

- Submission validation is correctly enforced
- Required fields cannot be bypassed
- Duplicate submissions are prevented
- Completed surveys are locked from modification

These behaviors are compliant with expected security constraints.

---

## 7. User Experience Observations

- Interface is responsive and usable across devices
- Navigation between surveys is functional
- Error messages are displayed when validation fails

However:
- lack of autosave significantly impacts usability
- lack of progress recovery reduces user confidence

---

## 8. Compliance Summary

The system is partially compliant with the Use Case.

### Fully Compliant Areas
- authentication-dependent access
- survey submission workflow
- validation of required fields
- final confirmation after submission
- prevention of duplicate submissions

### Non-Compliant Areas
- autosave functionality
- survey progress persistence
- resume incomplete survey feature
- incomplete survey notification system

---

## 9. Conclusion

While the system successfully implements the core survey submission workflow, it lacks critical state management features required by the Use Case.

The absence of autosave and resume mechanisms represents the most significant functional gap, directly impacting data integrity and user experience.

From a QA perspective, the system demonstrates:
- functional correctness at submission level
- but incomplete lifecycle management of survey interactions

---

## 10. Recommendation

To align with the Use Case requirements, the following improvements are recommended:

- implement real-time autosave of responses
- introduce persistent survey state storage
- enable resume functionality for incomplete surveys
- add dashboard indicators for pending surveys
- improve UX feedback for interrupted sessions