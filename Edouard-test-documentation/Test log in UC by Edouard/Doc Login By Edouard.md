# TEST REPORT — LOGIN

## 1. Introduction

This document presents the results of the tests performed on the **“Login”** use case for the *Student* role, as part of the **Student Survey Application** project.

The objective is to evaluate the compliance of the authentication system with the requirements defined in the Use Case, particularly in terms of:
- authentication security  
- handling of login attempts  
- access control  
- session management  
- protection against abuse  

---

## 2. Use Case Reference

### Key Requirements:

The system must:

- securely authenticate users  
- verify credentials (username/email + password)  
- redirect users to a role-based dashboard  
- track failed login attempts  
- temporarily lock the account:
  - after 3 failed attempts → 1 minute  
  - after 5 failed attempts → 3 minutes  
- protect against attacks (brute force, user enumeration)  
- securely handle password reset processes  

---

## 3. Test Scope

The tests covered:

- login with valid and invalid credentials  
- handling of login errors  
- behavior after multiple failed attempts  
- access control to protected pages  
- session management (login, logout, persistence)  
- “forgot password” functionality  
- system behavior under edge cases  

---

## 4. Observed User Experience

The actual observed behavior is as follows:

1. The user accesses the login page  
2. Enters username or email and password  
3. In case of error:
   - specific message is displayed depending on the error type  
4. In case of success:
   - user is redirected to the dashboard  
5. Logout redirects the user to the homepage  
6. No account suspension occurs after multiple failed attempts  

---

## 5. Comparative Analysis (Use Case vs Reality)

| Use Case Requirement | Current Implementation | Status |
|---------------------|----------------------|--------|
| User authentication | Functional | ✅ Compliant |
| Dashboard redirection | Functional | ✅ Compliant |
| Failed attempts handling | Missing | ❌ Not compliant |
| Lock after 3/5 attempts | Missing | ❌ Not compliant |
| Generic error messages | Not respected | ❌ Not compliant |
| Brute force protection | Missing | ❌ Not compliant |
| Access control (protected pages) | Functional | ✅ Compliant |
| Session management (login/logout) | Functional | ✅ Compliant |
| Password reset rate limiting | Missing | ❌ Not compliant |

---

## 6. Identified Issues

### 🔴 1. No account lock after failed login attempts

The system does not limit login attempts.

👉 **Impact:**
- vulnerable to brute-force attacks  
- high risk of account compromise  

---

### 🔴 2. Information disclosure via error messages (User Enumeration)

The system displays different messages depending on the error:

- user does not exist  
- invalid email  
- incorrect password  

👉 **Why this is a problem:**

This allows an attacker to:
- identify existing accounts  
- target specific users  

👉 **Impact:**
- critical security vulnerability  
- exposure of user information  

---

### 🟡 3. No rate limiting on password reset requests

The system allows unlimited password reset email requests.

👉 **Impact:**
- user spam  
- system abuse  
- email service overload  

---

## 7. Conclusion

The authentication system works at a basic functional level (login, redirection, session), but presents critical security gaps.

The main issues relate to:
- protection against attacks  
- error handling  
- abuse prevention  

Improvements are required to meet expected security standards.

---

## 8. Recommendations

- Implement account lockout after failed attempts  
- Use generic error messages  
- Add rate limiting to password reset  
- Strengthen overall security (e.g. CAPTCHA, logging, monitoring)  
