# Test Report: Review Past Feedback (UC-ReviewPastFeedback)

**Tester:** MUGISHO MERCI  
**Use Case:** UC-ReviewPastFeedback  
**Test Status:** ⚠️ **PARTIAL PASS** (Critical Issue Identified)

---

## What I tested

I tested the Review Past Feedback functionality for completed survey responses across all relevant sections. The focus was on verifying:

- access to the completed surveys page
- display of answers for each review section
- review of "Your Self" responses
- review of "Fullstack Questions" responses
- review of "Development" responses
- review of "Read About" responses
- review of "Read Home" responses
- review of "Frontend Questions" responses
- review of "Backend Questions" responses

### Test case details

#### TC-01 · Access Completed Surveys Page

**Steps:**
1. Navigated to the "My Completed Surveys" page.
2. Confirmed the list of completed surveys displayed.
3. Verified section grouping and page layout.

**Expected:** The completed surveys page loads successfully and survey sections are clearly organized.

**Observed:** ✅ The page loaded correctly and the survey list displayed as expected.

**Evidence:** `Screenshot_my_Surveys You Have Completed_page.png`

---

#### TC-02 · View "Your Self" Section Answers

**Steps:**
1. Opened the "Your Self" section.
2. Confirmed submitted answers were visible.
3. Checked answer layout and formatting.

**Expected:** User responses display correctly and are properly formatted.

**Observed:** ✅ Answers displayed correctly and formatting was consistent.

**Evidence:**
- `Screenshot my  Answers beedbank for: Your self page.png`
- `Screenshot my  Answers beedbank for: Your self section.png`

---

#### TC-03 · View "Fullstack Questions" Section Answers

**Steps:**
1. Opened the "Fullstack Questions" section.
2. Confirmed submitted answers were visible.
3. Checked formatting consistency with other sections.

**Expected:** Fullstack answers are visible and consistently formatted.

**Observed:** ✅ Answers displayed and matched the layout used in other sections.

**Evidence:** `Screenshot  my Answers for: Fullstack Questions feedbank.png`

---

#### TC-04 · View "Development" Section Answers

**Steps:**
1. Opened the "Your Development" section.
2. Confirmed submitted answers were visible.
3. Verified proper visual hierarchy.

**Expected:** Development answers display correctly and maintain their structure.

**Observed:** ✅ The section loaded and answers displayed correctly.

**Evidence:** `Screenshot my Answers for: your developpement section.png`

---

#### TC-05 · View "Read About" Section Answers

**Steps:**
1. Opened the "Read About" section.
2. Confirmed submitted answers were visible.

**Expected:** Read About answers display correctly.

**Observed:** ✅ Answers displayed correctly.

**Evidence:** `Screenshot Your Answers for: Read about section on the MKB Web site.png`

---

#### TC-06 · View "Read Home" Section Answers

**Steps:**
1. Opened the "Read Home" section.
2. Confirmed submitted answers were visible.

**Expected:** Read Home answers display correctly.

**Observed:** ✅ Answers displayed correctly.

**Evidence:** `Screenshot Your Answers for: Read the home section at MKB Web site..png`

---

#### TC-07 · View "Frontend Questions" Section Answers

**Steps:**
1. Opened the "Frontend Questions" section.
2. Confirmed submitted answers were visible.
3. Verified all question responses appeared.

**Expected:** Frontend Questions answers should appear in the review page.

**Observed:** ❌ The section loaded, but answers were not visible.

**Evidence:**
- `Screenshot it's the bug for my Answers beedbank for: Frontend Questions.png`
- `Screenshot bug frontend questions 1.png`

**Impact:** Users cannot review their Frontend Questions answers even though they were submitted successfully.

---

#### TC-08 · View "Backend Questions" Section Answers

**Steps:**
1. Opened the "Backend Questions" section.
2. Confirmed submitted answers were visible.
3. Verified all question responses appeared.

**Expected:** Backend Questions answers should appear in the review page.

**Observed:** ❌ The section loaded, but answers were not visible.

**Evidence:**
- `Screenshot it's bug for my Answers  feedbank for: Backend Questions.png`
- `Screenshot bug Backend questions 1.png`

**Impact:** Users cannot review their Backend Questions answers even though they were submitted successfully.

---

## What I observed

| Test case | Result | Severity |
| --- | --- | --- |
| Access Completed Surveys | Pass | — |
| Your Self section | Pass | — |
| Fullstack Questions section | Pass | — |
| Development section | Pass | — |
| Read About section | Pass | — |
| Read Home section | Pass | — |
| Frontend Questions section | Fail | High |
| Backend Questions section | Fail | High |

### Main observations

- The completed surveys page is accessible and survey sections are displayed clearly.
- Answers for Your Self, Fullstack Questions, Development, Read About, and Read Home are visible and correctly formatted.
- The Frontend Questions and Backend Questions sections load, but submitted answers are not displayed.
- This appears to be a section-specific display issue rather than a general data retrieval failure.

## What UC says in the document

The UC-ReviewPastFeedback document states that the system must:

- allow users to view historical feedback for completed surveys
- display all submitted survey responses by section
- provide clear navigation through completed survey review pages
- support review for both student and instructor roles
- maintain secure access and consistent presentation of response data

## What is respected against the UC

- ✅ The completed surveys page is accessible.
- ✅ The user can navigate to all review sections.
- ✅ Answers are displayed correctly for several sections.
- ✅ Page layout and section organization are consistent for supported sections.

## What is not respected against the UC

- ❌ Answers for Frontend Questions are not displayed.
- ❌ Answers for Backend Questions are not displayed.
- ❌ There is no evidence of filtering or export functionality in the current review page.
- ❌ The use case expectation for complete review visibility is not met.

## What I propose as solutions

- Fix the display bug for Frontend Questions and Backend Questions sections.
- Verify the data retrieval logic for these question categories.
- Add clear empty-state messaging when no review data is available.
- Improve survey review controls with filtering by survey title, date, and student name.
- Add export options such as CSV or PDF for completed survey review results.
- Include audit logging for feedback review actions to improve traceability.

---

## Defect report

### BUG-REVIEW-01 · Missing answer display for Frontend and Backend question sections

| Field | Details |
| --- | --- |
| **ID** | BUG-REVIEW-01 |
| **Title** | Submitted answers not displayed for Frontend and Backend question sections |
| **Type** | Functional / Display |
| **Severity** | High |
| **Use Case Reference** | UC-ReviewPastFeedback |
| **Expected** | All submitted answers should display in every review section |
| **Observed** | Frontend and Backend question responses are not visible |
| **Impact** | Users cannot fully review their completed survey responses |
| **Evidence** | `Screenshot it's the bug for my Answers beedbank for: Frontend Questions.png`, `Screenshot it's bug for my Answers  feedbank for: Backend Questions.png` |

---

## Recommendations & next steps

### Immediate actions
1. Investigate backend response handling for Frontend and Backend question sections.
2. Check frontend rendering logic for these sections.
3. Confirm data mapping and section labels for all review categories.

### Follow-up verification
1. Re-test all sections after the fix.
2. Validate that Frontend and Backend question answers display correctly.
3. Confirm the overall review flow is complete and consistent.

---

## Related documents

- `doc/usecase-diagram/usecases/UC-ReviewPastFeedback/UC-ReviewPastFeedback.md`
- `MUGISHO-MERCI-testing-documentation/Use Case Create Account testing create_Account/TEST_REPORT_create_account.md`
- `MUGISHO-MERCI-testing-documentation/test_provide_feedback/TEST_REPORT_student_survey.md`
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

