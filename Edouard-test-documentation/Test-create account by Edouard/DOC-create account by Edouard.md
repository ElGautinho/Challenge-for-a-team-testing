# TEST NOTES — Create Account (Student Role)

---

## What I am testing

I am testing:

> Student account creation workflow and registration validation behavior

The objective is to verify:

* registration process consistency
* collection of required student information
* validation behavior
* email handling
* password setup workflow
* compliance with the documented Create Account use case

---

## What I did (steps)

1. Opened the application homepage
2. Clicked on “Register as a student”
3. Observed the registration form fields
4. Entered:

   * username
   * email address
5. Submitted the registration form
6. Opened the email received from the system
7. Followed the password creation link
8. Created a password
9. Attempted login after account creation
10. Repeated the process with invalid email formats and weak passwords

---

## What I noticed

* The registration form only requests:

  * username
  * email address
* Academic level is not requested
* Programming languages are not requested
* Fake or invalid email formats can still be accepted
* Password creation is handled through an email link
* Weak passwords are accepted
* No password confirmation field exists
* No visible “pending approval” status is shown
* No visible restriction before administrator validation was observed

---

## What should have happened

Based on the documented use case:

* The Student registration form should collect:

  * academic level
  * programming languages
* Email validation should reject invalid addresses
* Password policy should enforce stronger security rules
* The system should clearly indicate that the account is pending approval
* Access should remain restricted until administrator validation

---

## Is this a problem?

Yes

---

## Summary of issues

### 1. Missing student-specific registration fields

**Observed behavior:**

* Academic level field is missing
* Programming languages selection is missing

**Impact:**
The system cannot collect essential student profile data required by the use case.

**Type:**
Missing Functionality / Business Logic

**Severity:**
High 🔴

---

### 2. Weak email validation behavior

**Observed behavior:**

* Invalid or fake email formats can still be accepted during registration

**Impact:**
Creates unreliable accounts and reduces overall data quality.

**Type:**
Validation / Data Quality

**Severity:**
High 🔴

---

### 3. Weak password setup workflow

**Observed behavior:**

* Weak passwords are accepted
* No password confirmation field exists

**Impact:**
Reduces account security and increases risk of user input mistakes.

**Type:**
Security / Validation

**Severity:**
Medium 🟡

---

### 4. Missing visible approval workflow

**Observed behavior:**

* No visible “pending approval” state is displayed
* No clear restriction before admin validation is observed

**Impact:**
Creates confusion regarding account activation status and diverges from the expected approval workflow.

**Type:**
Workflow / UX Consistency

**Severity:**
Medium 🟡

---

## Special notes

* Registration navigation works correctly
* Password creation email is successfully sent
* Password setup link functions correctly
* Student registration remains operational at a basic workflow level

However, the implementation is only partially aligned with the documented business requirements.

---

## Evidence

Observed during:

* registration form testing
* invalid input testing
* password setup workflow testing
* authentication verification after registration

Screenshots captured during:

* registration interface
* password setup process
* invalid email testing
* account creation workflow

---

## My thoughts / questions

* Is the missing academic profile information intentionally postponed for future implementation?
* Should approval workflow visibility be exposed directly to the user?
* Should stronger password policies be enforced at creation stage?

---

## Action taken

* Documented validation inconsistencies
* Identified missing business fields
* Verified email/password workflow behavior
* Continued testing of registration edge cases

---

## Conclusion

The registration workflow is functional at a basic operational level:

* users can register
* receive password setup emails
* create accounts successfully

However, several important business and validation requirements are missing, particularly regarding:

* student profile information
* email validation
* password security
* approval workflow visibility

From a QA perspective, the Create Account workflow is:

* operational
* but only partially compliant with the documented use case requirements

---
