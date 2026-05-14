# TEST REPORT — REVIEW PAST FEEDBACK (STUDENT ROLE)

## 1. Introduction

This document presents a structured QA analysis of the **“Review Past Feedback”** use case within the Student Survey Application.

The objective is to verify whether the system correctly allows a **Student user** to access, review, and interact with previously submitted survey responses, in compliance with the functional requirements defined in the Use Case specification.

Testing was conducted exclusively from the **Student perspective**, as per role restrictions.

---

## 2. Use Case Reference

### Core Requirements

The system must allow a Student to:

- access a list of completed surveys
- view survey metadata (title, date, status)
- open and review previously submitted responses
- ensure data privacy (only own submissions visible)
- optionally filter or search historical feedback
- maintain data persistence across sessions

---

## 3. Observed System Behavior Overview

The following behaviors were observed during testing:

- A “My Completed Surveys” menu is available after login
- Completed surveys are displayed in a list format
- Only survey titles are displayed in the list view
- Clicking a survey reveals detailed responses
- Data is persistent across refresh and navigation
- Access is correctly restricted to the authenticated student’s own data
- No export functionality is available for Student role (correct per specification)

---

## 4. Functional Compliance Analysis

| Requirement | Observed Behavior | Status |
|--------------|------------------|--------|
| Access to completed surveys | Available via menu | ✅ Compliant |
| Display of survey list | Functional | ✅ Compliant |
| Display of title | Visible | ✅ Compliant |
| Display of submission date | Missing | ❌ Non-compliant |
| Display of status | Missing | ❌ Non-compliant |
| View detailed responses | Functional | ✅ Compliant |
| Data privacy (own surveys only) | Correctly enforced | ✅ Compliant |
| Search functionality | Not implemented | ❌ Non-compliant |
| Filtering functionality | Not implemented | ❌ Non-compliant |
| Data persistence | Functional | ✅ Compliant |
| Export functionality (Student) | Not available | ✅ Compliant |

---

## 5. Key Issues Identified

### 🟡 1. Missing Survey Metadata (Date & Status)

The survey list only displays the **title**, while required metadata is absent.

#### Impact
- reduced traceability of submissions
- incomplete historical context
- partial compliance with Use Case specification

---

### 🟡 2. Missing Search and Filter Functionality

No mechanism is provided to:
- search surveys by title
- filter by date range
- refine historical results

#### Impact
- inefficient navigation in history
- reduced usability for users with many surveys
- deviation from Use Case requirements

---

### 🟢 3. Inline Display of Survey Details (UX Limitation)

Survey responses are displayed directly beneath the list rather than in a dedicated view.

#### Impact
- reduced readability
- weak separation of interface concerns
- suboptimal user experience design

---

## 6. Positive Observations

Despite the identified gaps, several core functionalities are correctly implemented:

- authentication-based access control is enforced
- students can only access their own submissions
- survey response data is correctly stored and retrieved
- session persistence is stable
- UI is responsive across devices
- completed surveys remain accessible after refresh

---

## 7. Security and Access Control Review

- Role-based access control is correctly implemented
- No cross-user data leakage detected
- No unauthorized access to other students’ feedback possible
- Export functionality is correctly restricted from Student role

➡️ Security baseline is considered **stable and compliant**

---

## 8. UX and Interface Observations

- Interface is responsive and stable
- Navigation is intuitive through dashboard menu
- Feedback details are accessible but not optimally structured
- Lack of filtering/search reduces usability in long-term usage

---

## 9. Compliance Summary

### Fully Compliant Areas
- authentication and access control
- survey listing and retrieval
- detailed response viewing
- data persistence
- role-based restrictions

### Partially Compliant Areas
- survey list metadata (missing date/status)
- UI structure for detail view

### Non-Compliant Areas
- search functionality
- filtering system

---

## 10. Conclusion

The system demonstrates a solid functional foundation for the **Review Past Feedback** use case, particularly in authentication, data access control, and response retrieval.

However, there are notable functional gaps in:
- metadata completeness
- history navigation tools (search/filter)

These limitations affect usability and do not fully align the implementation with the expected specification of the Use Case.

From a QA standpoint, the system is:
- **functionally stable**
- **secure at the access control level**
- but **incomplete in historical data usability features**

---

## 11. Recommendations

To fully align with the Use Case requirements, the following improvements are recommended:

- include survey submission date and status in history view
- implement search functionality for completed surveys
- add filtering by date range and/or survey title
- consider restructuring detail view into a dedicated page or modal
- improve UI separation between list and detailed response view