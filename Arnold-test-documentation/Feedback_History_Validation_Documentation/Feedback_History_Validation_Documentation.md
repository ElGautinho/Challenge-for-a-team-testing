# Validation Report – Review Past Feedback Module

## 1. What I Tested

I tested the **Review Past Feedback** module by verifying the following functionalities:

* User authentication (Student, Instructor, Administrator).
* Display of feedback history.
* Viewing detailed feedback responses.
* Search and filtering functionality.
* Handling cases where no results are found.
* Role-based permission control.
* Exporting feedback data to CSV and PDF formats.
* Data security during viewing and exporting operations.

---

## 2. What I Observed

### User Authentication

The system allows users to log in successfully according to their assigned roles and provides access only to authorized functionalities.

### Feedback History Display

The system correctly displays feedback history based on user roles:

* Students can view only their own feedback submissions.
* Instructors can view feedback related to surveys they created.
* Administrators can access all feedback records.

### Viewing Feedback Details

The system correctly displays detailed feedback information, including:

* survey questions,
* submitted responses,
* submission date,
* related survey information.

### Search and Filtering

Filtering functions work correctly using:

* date range,
* survey title,
* student name (for instructors and administrators).

The displayed results are updated according to the selected criteria.

### No Results Handling

When no matching feedback is found, the system displays an appropriate message and provides an option to clear or reset filters.

### Permission Control

Role-based access control works as expected:

* Students cannot access feedback submitted by other students.
* Instructors can access only surveys they created.
* Administrators have full access to all feedback records.

### Export Functionality

CSV and PDF export features work correctly, and files are downloaded successfully.

### Data Security

Viewing and exporting operations are protected through secure communication, and important actions are recorded in the system logs for auditing purposes.

---

## 3. What the Use Case Says

According to the **Review Past Feedback** use case, the system should:

* Allow students to review their own feedback history.
* Allow instructors to review responses for surveys they created.
* Allow administrators to access feedback across all surveys and users.
* Provide filtering by date range, survey title, and student name.
* Display detailed feedback responses.
* Support exporting feedback data in CSV and PDF formats.
* Prevent unauthorized access through role-based permissions.
* Log viewing and exporting activities for auditing purposes.
* Display appropriate messages when no feedback or matching results are found.

---

## 4. What I Recommend

After comparing the observed behavior with the use case requirements, no major issues were identified.

However, the following improvements could be considered:

* Add a clear confirmation message after a successful export.
* Improve the visibility of active filters.
* Enhance audit logs with additional details for better traceability.
* Verify that search and filter preferences are preserved for future sessions, as mentioned in the use case.

---

## 5. Conclusion

The testing performed confirms that the **Review Past Feedback** module meets the functional requirements defined in the use case.

Core functionalities, including authentication, feedback history display, detailed response viewing, filtering, exporting, permission management, and data security, operate correctly.

No critical issues were identified during testing.

### Final Result

**The "Review Past Feedback" use case has been successfully validated.**
