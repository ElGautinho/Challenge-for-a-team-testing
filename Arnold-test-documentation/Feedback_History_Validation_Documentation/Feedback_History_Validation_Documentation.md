# Validation Documentation for the “Review Past Feedback” Module

## Introduction

This document presents the validation results of the tests performed on the “Review Past Feedback” module of the system.
The main objective was to verify the proper functioning of all features available to students, instructors, and administrators.

After conducting different tests, all planned functionalities were executed successfully.

---

# 1. User Authentication

### Question:

Does the system allow users to log in correctly before accessing feedback history?

### Response:

Yes.
The system successfully authenticates users according to their roles (Student, Instructor, Administrator).
After login, each user can access only the functionalities permitted for their role.

### Result:

Functionality validated successfully.

---

# 2. Display of Feedback History

### Question:

Does the system correctly display the list of available feedback records?

### Response:

Yes.
The system successfully retrieves and displays completed surveys associated with each user:

* Students can view only their own submissions.
* Instructors can view feedback related to surveys they created.
* Administrators can access all feedback records.

The displayed information includes:

* survey title,
* submission date,
* status,
* response count.

### Result:

Functionality validated successfully.

---

# 3. Viewing Feedback Details

### Question:

Can users view detailed feedback responses?

### Response:

Yes.
When a user selects a feedback entry, the system correctly displays:

* survey questions,
* submitted answers,
* submission date,
* related survey information.

### Result:

Functionality validated successfully.

---

# 4. Filtering and Search Functionality

### Question:

Does the system correctly apply filters and search operations?

### Response:

Yes.
Filters based on:

* date range,
* survey title,
* student name (for instructors and administrators)

work correctly.

The system dynamically updates the displayed results according to the selected criteria.

### Result:

Functionality validated successfully.

---

# 5. Handling No Results Found

### Question:

Does the system respond correctly when no results are found?

### Response:

Yes.
When a search produces no results, the system displays clear messages such as:
“No feedback found” or “No matching results.”

The system also provides an option to reset or clear filters.

### Result:

Functionality validated successfully.

---

# 6. Permission Control and Security

### Question:

Does the system protect data according to user roles?

### Response:

Yes.
Role-based access control works correctly.

* Students cannot access feedback submitted by other students.
* Instructors can access only surveys they created.
* Administrators have full access privileges.

Any unauthorized access attempt is blocked and recorded in the system logs.

### Result:

Functionality validated successfully.

---

# 7. Exporting Feedback Data

### Question:

Does the system correctly export feedback data?

### Response:

Yes.
CSV and PDF export functionalities work correctly.

Generated files include:

* individual responses,
* aggregated statistics,
* survey information.

Downloads start successfully after file generation.

### Result:

Functionality validated successfully.

---

# 8. Data Security

### Question:

Is the data secure during viewing and exporting operations?

### Response:

Yes.
All communications are protected using HTTPS to ensure secure data transmission.

Important actions such as viewing, exporting, and unauthorized access attempts are logged with:

* date,
* time,
* user ID,
* survey ID.

### Result:

Functionality validated successfully.

---

# General Conclusion

After all tests performed on the “Review Past Feedback” module, the obtained results confirm that the system correctly satisfies the functional requirements defined in the specifications.

All major functionalities were tested successfully, including:

* authentication,
* feedback history display,
* detailed feedback viewing,
* filtering,
* exporting,
* permission management,
* data security.

The system operates correctly, reliably, and securely.

Final Validation:
All tests passed successfully.
