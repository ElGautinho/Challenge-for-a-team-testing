# TEST NOTES — Login (Student Role)

---

## What I am testing

I am testing:

> Student authentication workflow (“Login” use case)

The objective is to verify:

* authentication behavior
* access control
* failed login handling
* session management
* abuse prevention mechanisms
* compliance with security-related use case requirements

---

## What I did (steps)

1. Opened the login page
2. Attempted login with valid credentials
3. Attempted login with:

   * wrong password
   * invalid username
   * invalid email
4. Repeated failed login attempts multiple times
5. Checked whether account lock mechanisms existed
6. Tested access to protected pages without authentication
7. Logged in successfully and verified dashboard access
8. Logged out and verified session termination
9. Tested password reset functionality multiple times
10. Checked system behavior after refresh and navigation

---

## What I noticed

* Login with valid credentials works correctly
* Successful authentication redirects the user to the dashboard
* Different error messages are displayed depending on the failure type
* No temporary account lock occurs after repeated failed attempts
* No brute-force protection mechanism is visible
* Protected pages correctly require authentication
* Logout redirects the user to the homepage
* Password reset requests can be triggered repeatedly without limitation
* Session management behaves correctly during login/logout flow

---

## What should have happened

Based on the documented use case:

* The system should temporarily lock accounts after:

  * 3 failed attempts
  * 5 failed attempts
* Error messages should remain generic to avoid user enumeration
* Password reset requests should be rate-limited
* Brute-force protection mechanisms should exist
* Authentication and protected-page access should remain secure and controlled

---

## Is this a problem?

Yes

---

## Summary of issues

### 1. Missing account lock mechanism after failed login attempts

**Observed behavior:**

* Unlimited failed login attempts are allowed
* No temporary suspension occurs

**Impact:**
Exposes the system to brute-force attacks and credential guessing.

**Type:**
Security / Authentication

**Severity:**
High 🔴

---

### 2. Information disclosure through authentication error messages

**Observed behavior:**

* The system displays different messages for:

  * invalid username
  * invalid email
  * incorrect password

**Impact:**
Allows attackers to identify valid accounts and perform targeted attacks.

**Type:**
Security / User Enumeration

**Severity:**
High 🔴

---

### 3. Missing rate limiting on password reset requests

**Observed behavior:**

* Password reset requests can be triggered repeatedly without restriction

**Impact:**
May lead to:

* spam
* abuse
* unnecessary email load

**Type:**
Security / Abuse Prevention

**Severity:**
Medium 🟡

---

## Special notes

* Authentication itself works correctly
* Dashboard redirection functions properly
* Protected pages are inaccessible without login
* Session creation and logout behavior are stable

These areas are compliant with the expected use case behavior.

---

## Evidence

Observed during live testing through:

* valid/invalid authentication attempts
* repeated login failures
* protected-page access testing
* password reset testing
* session persistence verification

Screenshots captured during:

* login workflow
* authentication errors
* dashboard redirection
* password reset scenarios

---

## My thoughts / questions

* Should CAPTCHA or additional protection mechanisms be implemented?
* Is login attempt tracking planned for future versions?
* Why are authentication error messages exposing account existence?
* Should password reset requests include cooldown restrictions?

---

## Action taken

* Documented authentication inconsistencies
* Identified missing security protections
* Continued access-control and session testing

---

## Conclusion

The authentication workflow is functionally operational for standard login and session management. However, several important security protections expected by the use case are missing.

The main weaknesses are:

* absence of login attempt limitation
* exposure of account existence through error messages
* lack of password reset protection

From a QA perspective, the system is:

* functionally stable for authentication flow
* but insufficiently protected against abuse and enumeration attacks

---
