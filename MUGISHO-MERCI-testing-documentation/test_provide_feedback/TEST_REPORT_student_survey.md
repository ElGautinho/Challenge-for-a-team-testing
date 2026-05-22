# Test Report — Use Case: Provide Feedback / Student Survey (UC-ProvideFeedback)

| Field             | Details                                                                 |
| ----------------- | ----------------------------------------------------------------------- |
| **Tester**        | Mugisho Merci                                                           |
| **Application**   | MKB Survey Web Application                                              |
| **Use Case**      | UC-ProvideFeedback                                                      |
| **Reference doc** | `doc/usecase-diagram/usecases/UC-ProvideFeedback/UC-ProvideFeedback.md` |
| **Test folder**   | `MUGISHO-MERCI-testing-documentation/test_student_survey/`              |

---

## 1. What I Was Testing

I was testing the **student feedback / survey submission workflow** for the MKB Survey Application. This covers:

- Logging in as a student and accessing the home/dashboard page
- Viewing the list of all available surveys
- Opening, completing, and submitting a survey (referred to as "sodage" in the application)
- Verifying the post-submission confirmation state

---

## 2. Preconditions (from Use Case)

- The student has a verified and approved account.
- The student is logged into the system.
- At least one survey has been assigned and is available on the student's dashboard.

---

## 3. Test Cases Executed

### TC-01 · Student Home Page After Login

**Steps:**

1. Logged in as a student with valid credentials.
2. Observed the landing/home page displayed after authentication.

**Expected result (from UC-ProvideFeedback, Step 2):** The system authenticates the student and displays their dashboard / home page, which should include access to available surveys.

**Observed result:** ✅ The student home page loaded correctly after login. The MKB application home section was displayed with the expected layout and navigation.

**Screenshot:**

![Student Home Page](screenshots/student_home_page.png)

---

### TC-02 · Accessing the All Surveys Page

**Steps:**

1. From the student home page (TC-01), navigated to the "All Surveys" section or link.
2. Clicked the relevant navigation element to access the surveys list.

**Expected result (from UC-ProvideFeedback, Steps 3–4):** The system displays a list of all surveys available to the student, with their titles and access options.

**Observed result:** ✅ Clicking the "All Surveys" navigation element successfully loaded the surveys list page. The available surveys were displayed and accessible.

**Screenshot:**

![All Surveys Page](screenshots/all_surveys_page.png)

---

### TC-03 · Completing a Survey (Sodage)

**Steps:**

1. From the All Surveys page (TC-02), selected a survey to complete.
2. Read the instructions and answered all questions in the survey.
3. Navigated through the survey using the available controls.
4. Reviewed the answers before finalizing.

**Expected result (from UC-ProvideFeedback, Steps 5–7):** The system displays the survey with all questions, records responses as they are entered, allows navigation between questions, and enables the student to review their answers before submission.

**Observed result:** ✅ The survey (sodage) was displayed correctly. Questions were accessible and navigable. The completed state of the survey was reached after answering all fields.

**Screenshot:**

![Survey Completed — Ready to Submit](screenshots/survey_completed.png)

---

### TC-04 · Submitting the Survey and Confirmation

**Steps:**

1. After completing all questions in TC-03, clicked the final "Submit" button.
2. Observed the system response after submission.

**Expected result (from UC-ProvideFeedback, Steps 7–8 and the "Submitting Feedback" section):**

- The system validates that all required fields are filled.
- Confirms the submission.
- Securely stores the feedback.
- Displays a **thank-you / confirmation message** on the student's dashboard.
- The survey is marked as **completed**.

**Observed result:** ✅ The survey was submitted successfully. A post-submission screen was displayed confirming the action (labelled here as "After submission sodage"). The system acknowledged the submission and updated the view accordingly.

**Screenshot:**

![After Survey Submission](screenshots/after_survey_submission.png)

---

## 4. Summary Table

| TC ID | Test Case Description                                   | Status  | Severity |
| ----- | ------------------------------------------------------- | ------- | -------- |
| TC-01 | Student home page displyed correctly after login        | ✅ Pass | —        |
| TC-02 | All Surveys page accessible and lists available surveys | ✅ Pass | —        |
| TC-03 | Survey opened, questions answered, review possible      | ✅ Pass | —        |
| TC-04 | Survey submitted — confirmation screen displayed        | ✅ Pass | —        |

## 5. What I Saw

- I confirmed that the student dashboard loads correctly and exposes available surveys.
- The survey list is accessible and the survey content displays as expected.
- The student can complete the survey and receive a submission confirmation.
- The UI terminology uses "sodage" instead of "survey," which is inconsistent with the documentation.

## 6. What the UC Says

- UC-ProvideFeedback requires students to authenticate, access assigned surveys, answer all questions, and submit feedback securely.
- It expects automatic save of partial progress, required-field validation, and confirmation after submission.

## 7. What Was Not Respected Compared to the UC

- I did not verify partial progress saving for an abandoned survey.
- I did not verify that required questions block submission if left unanswered.
- The application uses the term "sodage," creating a terminology mismatch with the documented use case.

## 8. Professional Improvement Proposals

- Align UI wording with documentation by replacing "sodage" with "survey" or updating the documentation to match.
- Add an explicit progress-saving indicator when students leave a survey incomplete.
- Add a clear required-field validation summary before submission.
- Provide a confirmation page or toast message that explicitly states the survey was saved and submitted.
- Implement role-specific guidance on the student dashboard to show which surveys are currently available and which are completed.

---

## 9. Special Notes

> ✅ **The core Provide Feedback flow works end-to-end:** A logged-in student can navigate from the home page → All Surveys → open a survey → complete it → submit it → and receive a confirmation. This matches the Typical Course of Events described in UC-ProvideFeedback.

> ⚠️ **Not yet tested in this session:**
>
> - **Partial progress saving (Alternative Course 5a):** Exiting mid-survey and resuming later
> - **Required field validation (Alternative Course 7a):** Submitting with unanswered required questions
> - **No surveys available state (Alternative Course 1a):** Dashboard behaviour when no survey is assigned
> - **Data privacy:** Verifying that submitted responses are not visible to other students or unauthorized users
> - **Resubmission prevention:** Whether a student can submit the same survey multiple times

> ⚠️ **Terminology note:** The application uses the term **"sodage"** to refer to a survey. This term does not appear in the UC-ProvideFeedback documentation. This should be noted as a **terminology inconsistency** between the documentation and the implementation — it may cause confusion for new users and testers.

---

## 6. Points to Follow Up

### ⚠️ POINT-SURVEY-01 · Terminology Mismatch: "Sodage" vs "Survey"

| Field              | Details                                                         |
| ------------------ | --------------------------------------------------------------- |
| **ID**             | POINT-SURVEY-01                                                 |
| **Title**          | Application uses "sodage" — documentation uses "survey"         |
| **Type**           | Terminology Inconsistency / UX Concern                          |
| **Severity**       | Low                                                             |
| **Use Case Ref.**  | UC-ProvideFeedback (all references to "survey")                 |
| **Observed**       | Screenshots show "sodage" in the UI (not "survey")              |
| **Impact**         | Minor confusion for users and testers unfamiliar with the term  |
| **Recommendation** | Align UI terminology with the documentation, or update the docs |

---

## 7. Action Items

- [x] Documented all test observations with screenshots
- [ ] Test partial progress saving (exit mid-survey and resume)
- [ ] Test required field validation before submission
- [ ] Test the "no surveys available" edge case
- [ ] Verify data privacy — check that responses are not exposed
- [ ] Clarify the "sodage" vs "survey" terminology with the team
- [ ] Add the **`question`** or **`docs`** label for POINT-SURVEY-01 if raised as an issue

---

## 8. Related Documents

- [UC-ProvideFeedback](../../doc/usecase-diagram/usecases/UC-ProvideFeedback/UC-ProvideFeedback.md)
- [UC-Login](../../doc/usecase-diagram/usecases/UC-Login/UC-Login.md)
- [Test Report: Create Account](../test_create_account/TEST_REPORT_create_account.md)
- [Test Report: Login](../test_login/TEST_REPORT_login.md)
