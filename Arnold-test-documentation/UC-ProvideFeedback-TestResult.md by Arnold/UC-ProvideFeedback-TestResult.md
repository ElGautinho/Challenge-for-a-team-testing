# Validation Report – Provide Feedback Use Case

## 1. What I Tested

I tested the **Provide Feedback** use case to verify the following functionalities:

* Student authentication and dashboard access.
* Display of available surveys assigned to the student.
* Access to survey instructions and questions.
* Submission of responses using different question types (multiple choice, rating scales, and open-ended questions).
* Automatic saving of survey progress.
* Review and editing of responses before submission.
* Validation of required fields.
* Secure submission and storage of feedback data.
* Display of submission confirmation messages.
* Update of survey status after successful submission.

---

## 2. What I Observed

### Dashboard and Survey Access

The student was able to log in successfully and access the dashboard. The system correctly displayed the list of available surveys assigned to the student.

### Survey Completion

After selecting a survey, the system displayed all instructions and questions correctly. The student was able to answer different types of questions without any issues.

**Screenshot:**

![Survey Questions](<Capture d’écran (161).png>)

### Auto-Save Functionality

During survey completion, the system recorded responses in real time and automatically saved progress. This ensured that no information would be lost in the event of a disconnection or unexpected exit.

### Review and Validation

Before submission, the student was able to review and modify responses. The system correctly validated required fields and prevented submission when mandatory questions were not completed.

### Feedback Submission

After submission, the feedback was securely stored in the database, and the system displayed a confirmation message indicating that the survey had been submitted successfully.

**Screenshot:**

![Submission Confirmation](<Capture d’écran (160).png>)

### Survey Status Update

The system updated the survey status to indicate that the survey had been completed. The submitted feedback became available for future analysis by authorized personnel in an aggregated and secure format.

**Screenshot:**

![Completed Survey Status](<Capture d’écran (159).png>)

---

## 3. What the Use Case Says

According to the **Provide Feedback** use case, the system should:

* Allow students to access available surveys from their dashboard.
* Display survey instructions and questions.
* Support multiple question types, including multiple-choice, rating scale, and open-ended questions.
* Automatically save partial progress during survey completion.
* Allow students to review and edit their responses before submission.
* Validate required fields before accepting a submission.
* Securely store submitted feedback.
* Display a confirmation message after successful submission.
* Update the survey status once completed.
* Allow authorized personnel to access aggregated responses for analysis while maintaining student privacy and security.

---

## 4. What I Recommend

Based on the comparison between the observed behavior and the use case requirements, the functionality operates as expected.

The following improvements could further enhance the user experience:

* Display a visual indicator showing when auto-save is successfully completed.
* Provide a progress bar to show survey completion status.
* Include a feedback summary page before final submission.
* Add a notification for incomplete surveys when students log in again.

---

## 5. Conclusion

The execution of the **Provide Feedback** use case was successful.

All major functionalities defined in the use case were tested and worked correctly, including:

* dashboard access,
* survey completion,
* automatic saving,
* response review,
* field validation,
* secure submission,
* confirmation messaging,
* survey status updates.

No critical issues or system interruptions were encountered during testing.

### Final Result

**The "Provide Feedback" use case has been successfully validated and meets the specified functional requirements.**
