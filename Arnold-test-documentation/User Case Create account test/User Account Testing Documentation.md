# Test Report Documentation – User Account System

## Overview

This document summarizes the testing results for key user account functionalities, including:

* Account registration
* Password recovery
* User login

---

## Issue #5 – Registration Bug

### Description

During the account creation test, multiple issues were identified in the registration process.

### Observed Problems

#### 1. Role Selection Issue

* Only the "Student" role is visible
* The "Instructor" option is missing

#### 2. Student Form Issue

* When selecting "Student", additional fields do not appear:

  * Academic level
  * Programming languages

### Expected Behavior

* Both Student and Instructor roles should be available
* Selecting Student should dynamically display:

  * Academic level field
  * Programming languages field

### Actual Behavior

* Instructor role is not displayed
* Student-specific fields are not triggered or displayed

### Status

FAIL

### Possible Causes

* Missing or incorrect frontend rendering (HTML/JS)
* JavaScript event listener not working (on change of role)
* Backend not returning full role list

---

## Issue #15 – Password Recovery Test

### Objective

To verify the clarity and functionality of the password recovery process.

### Observations

* Password recovery email is successfully received
* Reset link is functional
* Password reset process completes without errors

### Clarity Evaluation

* Email content is clear and understandable
* User can follow instructions easily
* No confusion during the process

### Expected Behavior

* Clear instructions in email
* Simple and direct password reset process

### Status

PASS

### Conclusion

The password recovery system works correctly and provides a good user experience.

---

## Issue #8 – Student Login Test

### Observations

* Student can log in successfully with valid credentials
* System redirects to the correct dashboard
* No errors encountered

### Status

PASS

### Conclusion

Login functionality is stable and working as expected.

---

## Final Summary

| Feature           | Status | Notes                    |
| ----------------- | ------ | ------------------------ |
| Registration      | FAIL   | Critical UI/logic issues |
| Password Recovery | PASS   | Clear and functional     |
| Student Login     | PASS   | Works correctly          |

---

## Recommendations

* Fix role selection issue (add Instructor option)
* Ensure dynamic form rendering for Student fields
* Verify JavaScript logic for conditional fields
* Re-test registration after fixes

---

## Overall Conclusion

The system is partially functional. Core features like login and password recovery are working well, but the registration process requires immediate fixes before deployment.
