
# TEST NOTES - Create Account (Student)


# What I am testing

I am testing the Create Account functionality for a Student user, based on:

Use Case: UC-Create_Account.md
Scope: Manual functional testing
Preconditions
Before starting the test, I ensured that:

The application is accessible
I am NOT logged in
The email used for testing is NOT already registered
I understand the expected flow from the use case documentation
Happy Path Attempt
I attempted to follow the normal flow as described in the use case.

# What I did (steps)

I navigated to the application homepage

I clicked on the "User" button

A dropdown appeared with:

# Login
Register as a student
Since I do not have an account, I clicked "Register as a student"

# What I noticed (IMPORTANT)
Issue 1. Missing Role Selection (Major Gap)
The use case specifies that the user must choose between:

Student
Instructor
In the UI:

Only "Register as a student" is available
No option to register as an Instructor
This is a functional gap between the system and the documented use case.

# Screen shoot:

![alt text](<Capture d’écran (152).png>)

Issue 2. Missing Student-Specific Inputs (Level & Languages)
According to the use case:
A student must choose:

Academic level
Programming languages

In the application:

These fields are completely absent
The system proceeds directly to registration form
The system behaves as if the user were an Instructor, skipping a required step for Students.

# Continued Steps
After clicking "Register as a student", I was redirected to a registration form requesting:

Username
Email

# Screen shoot:

![alt text](<Capture d’écran (153).png>)

# Validation Behavior
I submitted the form with valid inputs
The system displayed:
"Registration complete. Please check your email, then visit the login page."

This corresponds to Step 6 in the use case (store + send email)



# Issue 4. Missing "Pending Approval" Flow (Critical)

Expected (from Use Case):

After registration:
Account should be in pending state
Requires administrator approval
User should NOT access the system immediately
Actual Behavior:
The user receives an email

The email allows:
Setting password
Immediate login
Direct access to dashboard

![alt text](<Capture d’écran (123).png>)

This completely bypasses:

Admin approval
Cohort assignment
Pending state

# Summary of Gaps

Issue	Type	Severity
Missing role selection (Instructor not available)	Functional gap	High
Missing student fields (level & languages)	Functional gap	High
No pending approval (direct access granted)	Critical functional issue	High


Role handling
Student-specific data
Approval workflow
These gaps should be addressed to ensure consistency between design and system behavior.
