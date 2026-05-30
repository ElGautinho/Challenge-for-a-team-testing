# Test Report: Review Past Feedback (UC-ReviewPastFeedback)

**Tester:** MUGISHO MERCI  
**Use Case:** UC-ReviewPastFeedback  
**Test Status:** ⚠️ **PARTIAL PASS** (Critical Issue Identified)

---

## Executive Summary

This test report documents the comprehensive testing of the "Review Past Feedback" use case functionality. The primary objective was to verify that users can successfully view, access, and review their completed survey responses.

**Overall Result:** The core functionality works correctly, but a **critical display bug** has been identified affecting the visibility of user responses for specific survey sections (Frontend Questions and Backend Questions).

---

## 1. Test Scope & Objectives

### 1.1 Scope
This test covers the following functionality:
- Navigation to completed surveys
- Display of survey responses organized by sections
- Visibility and rendering of user answers across different survey categories
- Layout and presentation of feedback data

### 1.2 Test Objectives
- ✅ Verify users can access "My Completed Surveys" page
- ✅ Confirm survey responses are retrieved correctly from the system
- ✅ Validate that user answers display properly for all survey sections
- ❌ Identify and document any display or rendering issues

---

## 2. Test Environment

| Configuration | Details |
|:---|:---|
| **OS** | Linux |
| **Browser** | Chrome/Firefox |
| **Application URL** | MKB Web Site - Feedback Survey Section |
| **Test Type** | Manual Functional Testing |
| **Test Approach** | User Interface Verification & Visual Inspection |

---

## 3. Test Cases Executed

### 3.1 Test Case 1: Access Completed Surveys Page
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Navigate to "My Completed Surveys" | Page loads successfully | Page loads successfully ✅ |
| 2. Verify survey list displays | List of completed surveys visible | Survey list displayed ✅ |
| 3. Verify page layout | Surveys organized by sections/categories | Properly organized ✅ |

**Evidence:** Screenshot: `Screenshot_my_Surveys You Have Completed_page.png`

---

### 3.2 Test Case 2: View "Your Self" Section Answers
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Your Self" section | Section loads | Section loads ✅ |
| 2. Verify answers display | User responses visible | Answers visible and correctly formatted ✅ |
| 3. Verify layout | Answers properly structured | Layout correct ✅ |

**Evidence:** 
- Screenshot: `Screenshot my  Answers beedbank for: Your self page.png`
- Screenshot: `Screenshot my  Answers beedbank for: Your self section.png`

---

### 3.3 Test Case 3: View "Fullstack Questions" Section Answers
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Fullstack Questions" section | Section loads | Section loads ✅ |
| 2. Verify answers display | User responses visible | Answers visible and properly displayed ✅ |
| 3. Check formatting consistency | Answers match other sections' format | Layout consistent ✅ |

**Evidence:** Screenshot: `Screenshot  my Answers for: Fullstack Questions feedbank.png`

---

### 3.4 Test Case 4: View "Development Section" Answers
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Your Development" section | Section loads | Section loads ✅ |
| 2. Verify answers display | User responses visible | Answers visible ✅ |
| 3. Verify visual hierarchy | Content properly formatted | Format correct ✅ |

**Evidence:** Screenshot: `Screenshot my Answers for: your developpement section.png`

---

### 3.5 Test Case 5: View "Read About Section" Answers
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Read About" section | Section loads | Section loads ✅ |
| 2. Verify answers display | User responses visible | Answers visible ✅ |

**Evidence:** Screenshot: `Screenshot Your Answers for: Read about section on the MKB Web site.png`

---

### 3.6 Test Case 6: View "Read Home Section" Answers
**Status:** ✅ **PASS**

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Read Home" section | Section loads | Section loads ✅ |
| 2. Verify answers display | User responses visible | Answers visible ✅ |

**Evidence:** Screenshot: `Screenshot Your Answers for: Read the home section at MKB Web site..png`

---

### 3.7 Test Case 7: View "Frontend Questions" Answers
**Status:** ❌ **FAIL** - Critical Display Bug

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Frontend Questions" section | Section loads | Section loads but answers NOT visible ❌ |
| 2. Verify answers display | User responses should be visible | **Answer data is missing from display** ❌ |
| 3. Verify all question responses shown | All questions answered should appear | **No responses displayed** ❌ |

**Evidence:** 
- Screenshot: `Screenshot it's the bug for my Answers beedbank for: Frontend Questions.png`
- Screenshot: `Screenshot bug frontend questions 1.png`

**Impact:** Users cannot review their Frontend Questions answers through the UI, even though the answers were successfully submitted.

---

### 3.8 Test Case 8: View "Backend Questions" Answers
**Status:** ❌ **FAIL** - Critical Display Bug

| Step | Expected Result | Actual Result |
|:---|:---|:---|
| 1. Access "Backend Questions" section | Section loads | Section loads but answers NOT visible ❌ |
| 2. Verify answers display | User responses should be visible | **Answer data is missing from display** ❌ |
| 3. Verify all question responses shown | All questions answered should appear | **No responses displayed** ❌ |

**Evidence:**
- Screenshot: `Screenshot it's bug for my Answers  feedbank for: Backend Questions.png`
- Screenshot: `Screenshot bug Backend questions 1.png`

**Impact:** Users cannot review their Backend Questions answers through the UI, despite successful form submission.

---

## 4. Issues & Defects Identified

### 4.1 Critical Issue: Missing Answers Display for Frontend & Backend Questions

**Issue ID:** BUG-001  
**Severity:** 🔴 **CRITICAL**  
**Status:** 🔴 **OPEN**  
**Priority:** P0 (Highest)

#### Description
User responses for "Frontend Questions" and "Backend Questions" survey sections are not visible on the "My Completed Surveys" page, while answers for other sections (Your Self, Fullstack Questions, Development, etc.) display correctly.

#### Expected Behavior
When accessing the "My Completed Surveys" page, all submitted survey responses should be displayed consistently across all survey sections, including:
- Frontend Questions
- Backend Questions

#### Actual Behavior
- The Frontend Questions section appears but shows no answer data
- The Backend Questions section appears but shows no answer data
- Other sections display answers correctly
- This inconsistency suggests a data retrieval or rendering issue specific to these two sections

#### Steps to Reproduce
1. Complete a survey that includes "Frontend Questions" and "Backend Questions"
2. Navigate to "My Completed Surveys" page
3. Observe that answers are visible for "Your Self", "Fullstack Questions", "Development Section", etc.
4. Scroll to or access "Frontend Questions" section → **Answers not displayed**
5. Scroll to or access "Backend Questions" section → **Answers not displayed**

#### Evidence
- Screenshot: `Screenshot it's the bug for my Answers  feedbank for: Backend Questions.png`
- Screenshot: `Screenshot it's the bug for my Answers beedbank for: Frontend Questions.png`
- Screenshot: `Screenshot bug Backend questions 1.png`
- Screenshot: `Screenshot bug frontend questions 1.png`

#### Root Cause Analysis

**Possible Causes:**
1. **Backend Issue:** Survey questions endpoint not returning data for Frontend/Backend question types
2. **Filtering Logic:** Data filter or query parameter incorrectly excluding these question categories
3. **Frontend Rendering:** Component-specific rendering bug for these question types
4. **Data Mapping:** Incorrect data binding or variable mapping for these sections

#### Affected Users
- All users (Students and Instructors) who attempt to review their answers for Frontend or Backend Questions

---

## 5. Summary of Test Results

| Test Case | Result | Notes |
|:---|:---|:---|
| 3.1 - Access Completed Surveys | ✅ PASS | Page loads correctly |
| 3.2 - Your Self Section | ✅ PASS | Answers display correctly |
| 3.3 - Fullstack Questions | ✅ PASS | Answers display correctly |
| 3.4 - Development Section | ✅ PASS | Answers display correctly |
| 3.5 - Read About Section | ✅ PASS | Answers display correctly |
| 3.6 - Read Home Section | ✅ PASS | Answers display correctly |
| 3.7 - Frontend Questions | ❌ FAIL | Critical display bug detected |
| 3.8 - Backend Questions | ❌ FAIL | Critical display bug detected |

**Overall Test Result:** ⚠️ **75% PASS RATE (6/8 cases passed)**

## 5. What I Saw

- I saw that most survey sections display answers correctly and the completed survey list is accessible.
- The "Frontend Questions" and "Backend Questions" sections load but do not display the submitted answers.
- Other review sections such as Your Self, Fullstack Questions, Development, Read About, and Read Home render data as expected.
- This indicates a targeted display issue rather than a complete breakdown of the review feedback system.

## 6. What UC Says

- UC-ReviewPastFeedback requires users to view historical feedback for completed surveys.
- It specifies that instructors should be able to see the responses for surveys they created and that students should see their own submissions.
- It also requires filtering, detailed response views, and export options for review data.
- Role-based access and secure visibility controls are part of the expected behavior.

## 7. What Was Not Respected Compared to the UC

- Responses for Frontend Questions and Backend Questions are not displayed, violating the feedback review requirement.
- There is no visible evidence of filtering or export functionality in the current UI.
- The report does not show audit or access logging, which is part of the documented use case.

## 8. Professional Improvement Proposals

- Fix the data retrieval or rendering bug for Frontend and Backend question sections.
- Add filtering controls by survey title, date range, and student name for instructors.
- Introduce export options such as CSV and PDF for completed feedback reports.
- Implement clearer empty-state messaging for sections that have no data.
- Add audit logging for feedback view actions to strengthen traceability and security.

## 9. Recommendations & Next Steps

### 9.1 Immediate Actions Required
1. **Investigate Backend API:** Verify that the `/api/surveys/responses` endpoint correctly returns data for Frontend and Backend question types.
2. **Debug Frontend Component:** Check the rendering logic for these specific question categories.
3. **Review Data Schema:** Confirm that Frontend/Backend questions are correctly mapped in the survey response data model.

### 9.2 Quality Assurance Verification
1. Once the issue is fixed, re-test all 8 test cases.
2. Verify data consistency across all browsers.
3. Perform cross-browser compatibility testing (Chrome, Firefox, Safari, Edge).
4. Test with multiple user accounts to ensure the issue is not user-specific.

### 9.3 Regression Testing
After bug fix implementation:
- Verify other survey sections still display correctly.
- Test with surveys containing all question types.
- Validate that export functionality (CSV/PDF) includes Frontend/Backend answers.

---

## 10. Test Conclusion

The "Review Past Feedback" functionality is **partially operational** with a critical defect that prevents users from viewing their answers for Frontend and Backend survey sections. While the core navigation and display mechanism works correctly for other sections, the identified bug represents a significant gap in feature completeness.

**Recommendation:** Do not approve for production release until the Frontend Questions and Backend Questions display issue is resolved and re-tested.

---

## Appendix: Screenshots Reference

| Screenshot File | Purpose |
|:---|:---|
| `Screenshot_my_Surveys You Have Completed_page.png` | Main "My Completed Surveys" page overview |
| `Screenshot my  Answers beedbank for: Your self page.png` | Your Self section - Full page view |
| `Screenshot my  Answers beedbank for: Your self section.png` | Your Self section - Alternative view |
| `Screenshot  my Answers for: Fullstack Questions feedbank.png` | Fullstack Questions section (PASS) |
| `Screenshot my Answers for: your developpement section.png` | Development section (PASS) |
| `Screenshot Your Answers for: Read about section on the MKB Web site.png` | Read About section (PASS) |
| `Screenshot Your Answers for: Read the home section at MKB Web site..png` | Read Home section (PASS) |
| `Screenshot it's the bug for my Answers beedbank for: Frontend Questions.png` | Frontend Questions - **BUG** |
| `Screenshot bug frontend questions 1.png` | Frontend Questions - **BUG** (Alternative) |
| `Screenshot it's bug for my Answers  feedbank for: Backend Questions.png` | Backend Questions - **BUG** |
| `Screenshot bug Backend questions 1.png` | Backend Questions - **BUG** (Alternative) |

---

**Report Prepared By:** MUGISHO MERCI  
**Test Environment:** MKB Web Site - Feedback Survey Module  
**Classification:** Internal Test Documentation

