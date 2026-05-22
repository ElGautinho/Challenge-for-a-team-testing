# UC-Instructor Test Report

## 1. Context and Scope
This report is written based on screenshots I collected in the folder `test-UC-instructor/screenshot test uc intructor`.
My goal was to evaluate the application’s compliance with the instructor’s main usage, in particular:
- user login
- survey management
- question management
- access to responses and feedback
- the student journey associated with a published survey

## 2. What Was Tested
### 2.1 Authentication
- I checked the standard WordPress login page (`login instructeur.png`).
- I verified the presence of the `Username or Email Address` / `Password` form.
- I confirmed the presence of the link `Register | Lost your password?`.

### 2.2 Instructor Interface
- I observed the WordPress admin dashboard for the instructor (`Dashborard instructeur.png`).
- I noted the main navigation menu containing: `Dashboard`, `Posts`, `Questions`, `Survey Responses`, `Surveys`, etc.

### 2.3 Survey Management
- I reviewed the list of existing surveys (`all Surveys interface.png`).
- I checked the survey creation interface (`Add New Survey interface.png`).
- I confirmed the presence of the following fields: title, description, start date, end date, publish status, visibility.

### 2.4 Question Management
- I examined the list of questions linked to surveys (`all Questions interface .png`).
- I verified the question creation interface (`add New Question interface.png`).
- I noted the fields present: title, associated survey, question type, answer options, required field.

### 2.5 Access to Responses and Feedback
- I accessed the `Survey Responses` view available in the menu (`Survey Responses .png`).
- I saw a feedback record with a message labeled `Instructor Feedback` (`instructor feedback.png`).
- I observed a response list screen showing “No surveys found” when no data was present.

### 2.6 Student Journey
- I reviewed the student survey page visible on the front-end (`my survey and my question for interface student Frontend & Full Stack Development Skills Survey.png`).
- I confirmed the display of questions, multiple-choice options, text fields, and the `Submit` button.

## 3. What I Observed
### 3.1 Main Observations
- The application relies on a standard WordPress back-office interface.
- The instructor menu clearly exposes the expected modules: `Surveys`, `Questions`, and `Survey Responses`.
- The survey creation form includes opening/closing dates, which matches the UC.
- The survey publication module resembles a WordPress post, with Draft/Published status.
- The question creation module allows linking a question to a survey, selecting a type, and defining options.
- The student journey is functional and displays a survey titled `Frontend & Full Stack Development Skills Survey`.
- Instructor feedback is visible in the detail of a response, confirming a feedback review concept.

### 3.2 Observed Behaviors
- The back-office uses a standard WordPress `Version 6.9.4 / 7.0`.
- The dashboard mainly contains WordPress widgets, not a dedicated instructor business summary.
- A `Publish` button exists for surveys, but the screen does not explicitly show a preview or a business preview workflow.
- The `Survey Responses` list sometimes shows `No surveys found`, which may indicate a response-to-survey linkage issue or an empty test state.

## 4. What the UCs Specify
### 4.1 UC-ManageSurvey
- The instructor must be able to create, edit, and delete a survey.
- The system must offer question types such as multiple choice, text, true/false, etc.
- The instructor must be able to set title, description, dates, questions, and preview.
- The system must handle saving and errors (empty title field, save failure).

### 4.2 UC-ProvideFeedback
- Students must authenticate and see their dashboard.
- They must be able to select a survey, answer questions, save responses, and submit.
- The system must display the questions and securely store the responses.

### 4.3 UC-ReviewPastFeedback
- The instructor must see the feedback history for their surveys.
- They must be able to filter, view detailed responses, and export results.
- The views must respect access rights and show only the appropriate surveys.

## 5. Non-Conformities Observed Compared to the UCs
### 5.1 Incomplete Feedback Review Functionality
- UC-ReviewPastFeedback expects a list of responses and detailed history access.
- The `Survey Responses .png` screenshot shows an empty screen (`No surveys found`), suggesting feedback review is missing or poorly linked.
- The instructor does not clearly have a business dashboard grouping results/feedback.

### 5.2 Lack of Dedicated Instructor Business Visibility
- The WordPress dashboard is generic and does not present clear indicators such as: number of published surveys, responses received, survey status.
- UC-ManageSurvey and UC-ReviewPastFeedback require a more business-oriented interface than a simple WordPress dashboard.

### 5.3 Lack of Evidence for Export and Filtering
- Nothing in the screenshots shows a CSV/PDF export feature or advanced filtering of responses.
- UC-ReviewPastFeedback mentions filtering by title, date, and export, which are not visible.

### 5.4 Possible Terminology Inconsistency
- The screenshots show a WordPress menu with `Questions`, `Surveys`, `Survey Responses`, while the `U-Instructor.md` file references “ProvideFeedback” and “Review Past Feedback”.
- The journey is partially integrated, but the implementation appears more oriented toward WordPress management than a pure pedagogical workflow.

## 6. Improvement Proposals
### 6.1 Strengthen Instructor Dashboard Coherence
- Create a dedicated instructor dashboard with these widgets:
  - number of active surveys
  - number of responses received
  - alerts for surveys closing soon
  - quick access to surveys, questions, and feedback

### 6.2 Complete the `Survey Responses` Module
- Ensure all submitted responses are listed correctly.
- Add filters by survey, student, and date.
- Add access to detailed response views.
- Implement CSV/PDF export in line with the UC.

### 6.3 Clarify the Survey Creation Workflow
- Add a wizard or business guidance on the `Add New Survey` page to outline the steps.
- Include a visible and understandable business `Preview` button.
- Verify that start/end dates are saved correctly and warn if the end date is before the start date.

### 6.4 Improve the Instructor Interface Experience
- Replace or complement the generic WordPress view with a more structured pedagogical management interface.
- Hide WordPress elements that are not useful to the instructor (for example `Posts` if not needed).
- Add navigation oriented around “Surveys”, “Questions”, “Responses”, “History”.

### 6.5 Verify Permissions and Roles
- Ensure students only access available surveys and not the WordPress admin.
- Ensure the instructor only sees their own surveys and responses, in accordance with UC-ReviewPastFeedback.
- Apply strict role control on `Questions`, `Surveys`, and `Survey Responses` pages.

### 6.6 Additional Proposals to Significantly Improve the Platform
- Add ready-to-use survey templates to save instructor time.
- Offer a step-by-step survey creation assistant (wizard) enforcing best practices.
- Implement a notification system to alert the instructor when a survey is about to expire or when a response threshold is reached.
- Add a lightweight analytics dashboard with KPIs: response rate, average completion time, average satisfaction.
- Offer a “duplicate survey” function to quickly reuse an existing questionnaire.
- Integrate a mobile preview of the survey to validate smartphone and tablet display.
- Add tags or categories to organize surveys and questions by theme.
- Provide standard question templates and libraries of common questions.
- Enable export of consolidated reports in PDF or Excel for stakeholders.
- Add internal comment/annotation functionality so the instructor can note results.
- Implement a survey change history to track edits to questions and dates.
- Add real-time validation on critical fields (title, dates, required questions).
- Support advanced question types (Likert scales, matrices, multiple categories).
- Offer a global search interface for surveys, questions, and responses.
- Include contextual help on each screen to support the instructor.

## 7. Conclusion
I found that the application provides a relevant functional base for the instructor: login, survey creation, question addition, publication, and student survey viewing.
However, the feedback/history section remains incomplete and the presentation is too generic for an expert instructor use case.

> Key recommendation: consolidate the `Survey Responses` module and enrich the instructor dashboard to fully meet the UC requirements and facilitate pedagogical use of the results.
