# Test Report — Use Case: Provide Feedback / Student Survey (UC-ProvideFeedback)

| Field             | Details                                                                 |
| ----------------- | ----------------------------------------------------------------------- |
| **Tester**        | Mugisho Merci                                                           |
| **Application**   | MKB Survey Web Application                                              |
| **Use Case**      | UC-ProvideFeedback                                                      |
| **Reference doc** | `doc/usecase-diagram/usecases/UC-ProvideFeedback/UC-ProvideFeedback.md` |
| **Test folder**   | `MUGISHO-MERCI-testing-documentation/test_student_survey/`              |

---

## What I tested

I tested the student feedback survey workflow in the MKB Survey Web Application by verifying the following scenarios:

- login as a student and access the dashboard
- navigate to the available surveys list
- open and complete a survey
- submit the survey and verify the confirmation screen
- observe the terminology used in the UI

### Test case details

#### TC-01 · Student Home Page After Login

**Steps:**
1. Logged in as a student with valid credentials.
2. Observed the landing/home page after authentication.

**Expected:** The student dashboard loads successfully and displays survey navigation options.

**Observed:** ✅ The student home page loaded correctly and showed the expected home section layout.

**Evidence:**
- `screenshots/student_home_page.png`

---

#### TC-02 · Accessing the All Surveys Page

**Steps:**
1. From the student home page, navigated to the "All Surveys" page.
2. Confirmed the list of available surveys.

**Expected:** The system displays all surveys available to the student with clear access options.

**Observed:** ✅ The All Surveys page loaded successfully and the available surveys were visible.

**Evidence:**
- `screenshots/all_surveys_page.png`

---

#### TC-03 · Completing a Survey

**Steps:**
1. Selected a survey from the All Surveys page.
2. Read instructions and answered all questions.
3. Navigated through the survey and reviewed responses.

**Expected:** The survey loads correctly, records answers, and allows review before submission.

**Observed:** ✅ The survey loaded correctly, questions were accessible, and the student reached the end state after completing all fields.

**Evidence:**
- `screenshots/survey_completed.png`

---

#### TC-04 · Submitting the Survey and Confirmation

**Steps:**
1. After completing all questions, clicked the final submit button.
2. Observed the post-submission response.

**Expected:** The system validates required fields, stores feedback, and displays a confirmation message.

**Observed:** ✅ The survey submitted successfully and a confirmation screen was displayed.

**Evidence:**
- `screenshots/after_survey_submission.png`

---

## What I observed

- The student dashboard loads correctly and displays available survey navigation.
- The All Surveys page is accessible and presents the list of surveys.
- The survey content is displayed correctly and allows the student to complete answers.
- The survey submission process works and shows a confirmation state.
- The application uses the term "sodage" instead of "survey," creating a terminology inconsistency.

## What UC says in the document

The UC-ProvideFeedback document indicates that the system should:

- allow a student to log in and access assigned surveys
- display available surveys clearly
- present the survey questions and collect answers
- validate required fields and allow review before submission
- store feedback and show confirmation after submission

## What is respected against the UC

- ✅ The student dashboard is accessible after login.
- ✅ The All Surveys page is available and surveys are listed.
- ✅ The survey loads and allows answer entry.
- ✅ The survey submission workflow completes successfully.

## What is not respected against the UC

- ❌ Partial progress saving was not verified in this session.
- ❌ Required-field validation was not tested.
- ❌ The UI uses the term "sodage," which does not match the documented use case terminology.

## What I propose as solutions

- Align the UI terminology with the documentation by using "survey" consistently.
- Add a visible progress-saving indicator for incomplete surveys.
- Implement and verify required-field validation before submission.
- Provide explicit confirmation messaging after submission.
- Add dashboard guidance for available versus completed surveys.

---

## Defect report

### POINT-01 · Terminology inconsistency: "sodage" vs "survey"

| Field | Details |
| ----- | ------- |
| **ID** | POINT-01 |
| **Title** | UI uses "sodage" instead of "survey" |
| **Type** | UX / Terminology |
| **Severity** | Low |
| **Use Case Reference** | UC-ProvideFeedback |
| **Observed** | The application label reads "sodage" while documentation uses "survey" |
| **Impact** | Confusion for users and testers unfamiliar with the term |
| **Recommendation** | Align UI wording with documentation or update the UC terminology to match |

---

## Recommendations & next steps

- Verify partial progress saving for a survey when the student exits before completion.
- Test required-field validation by attempting submission with missing answers.
- Confirm the no-surveys-assigned scenario on the student dashboard.
- Review the terminology used in the application and align it with the documentation.

---

## Related documents

- `doc/usecase-diagram/usecases/UC-ProvideFeedback/UC-ProvideFeedback.md`
- `doc/usecase-diagram/usecases/UC-Login/UC-Login.md`
- `MUGISHO-MERCI-testing-documentation/Use Case Create Account testing create_Account/TEST_REPORT_create_account.md`
- `MUGISHO-MERCI-testing-documentation/Use Case Login testing report/TEST_REPORT_login.md`
