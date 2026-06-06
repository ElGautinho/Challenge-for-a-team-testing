# Test Report — Use Case: Login (UC-Login)

| Field             | Details                                             |
| ----------------- | --------------------------------------------------- |
| **Tester**        | Mugisho Merci                                       |
| **Date**          | 2026-05-13                                          |
| **Application**   | MKB Survey Web Application                          |
| **Use Case**      | UC-Login                                            |
| **Reference doc** | `doc/usecase-diagram/usecases/UC-Login/UC-Login.md` |
| **Test folder**   | `MUGISHO-MERCI-testing-documentation/test_login/`   |

---

## What I tested

I tested the login flow of the MKB Survey Web Application through the following scenarios:

- access to the login interface
- login attempt with an unregistered email
- repeated login attempts with an incorrect password
- login with valid credentials and redirect to the dashboard
- access to the password recovery page

### Test case details

#### TC-01 · Access to the Login Interface

**Steps:**
1. Opened the MKB Survey Application.
2. Navigated to the login page.

**Expected:** The login form should display email and password fields, a "Forgot password?" link, and a registration option.

**Observed:** ✅ The login page loaded successfully with the expected fields and links.

**Evidence:**

![Login Page](screenshots/login_page.png)

---

#### TC-02 · Login with Unregistered Email

**Steps:**
1. Entered an email address that does not exist in the system.
2. Entered any password.
3. Clicked "Login." 

**Expected:** The system should display an error indicating invalid credentials or an unregistered user.

**Observed:** ✅ The login attempt was blocked and the UI displayed a **"user not found"** error.

**Evidence:**

![User Not Found Error](screenshots/user_not_found_error.png)

---

#### TC-03 · Repeated Failed Login Attempts

**Steps:**
1. Entered a valid email with an incorrect password.
2. Repeated this at least five times.
3. Observed the system behavior after each attempt.

**Expected:** According to UC-Login, the system should lock the account or block login after repeated failures.

**Observed:** ❌ No lockout occurred. The application continued to accept login attempts without delay, CAPTCHA, or any lockout message.

**Severity:** High — this is a significant security gap that exposes the system to brute-force attacks.

**Evidence:**

![No Lockout After Multiple Attempts](screenshots/no_lockout_after_multiple_attempts.png)

---

#### TC-04 · Valid Login and Redirect to Dashboard

**Steps:**
1. Entered a valid registered email and correct password.
2. Clicked "Login." 

**Expected:** The system should authenticate the user and redirect them to the appropriate dashboard.

**Observed:** ✅ The user authenticated successfully and was redirected to the dashboard.

**Evidence:**

![Dashboard After Login](screenshots/dashboard_after_login.png)

---

#### TC-05 · Access to Password Recovery Page

**Steps:**
1. Clicked the "Forgot password?" link from the login page.

**Expected:** The application should open the password recovery interface.

**Observed:** ✅ The password recovery page loaded correctly and displayed the email entry form.

**Evidence:**

![Lost Password Page](screenshots/lost_password_page.png)

---

## What I observed

| TC ID | Test case | Result | Severity |
| ----- | --------- | ------ | -------- |
| TC-01 | Access to the login interface | Pass | — |
| TC-02 | Unregistered email | Pass | — |
| TC-03 | Repeated failed login attempts | Fail | High |
| TC-04 | Valid login and redirect | Pass | — |
| TC-05 | Access to password recovery | Pass | — |

### Main observations

- The login interface is accessible and clearly presented.
- The system correctly rejects unregistered users.
- The password recovery entry point is available and functional.
- The valid login flow works and redirects to the dashboard.
- The lockout mechanism after repeated failed login attempts is not implemented.

## What UC says in the document

The `UC-Login` document specifies that the system should:

- allow access to the login interface
- handle valid and invalid credentials
- block or delay access after repeated failed attempts
- redirect each user role to the appropriate dashboard
- provide access to password recovery

## What is respected against the UC

- ✅ The login interface is accessible.
- ✅ Invalid credentials are rejected.
- ✅ The password recovery page is available.
- ✅ Successful login redirects to the dashboard.

## What is not respected against the UC

- ❌ The lockout or delay after repeated failed login attempts is not implemented.
- ❌ No progressive protection (delay, CAPTCHA, or lockout) is applied.
- ❌ Role-specific dashboard redirect verification was not covered in this test.

## What I propose as solutions

- Implement an account lockout mechanism after 3 to 5 failed login attempts.
- Display a clear message when the account is temporarily locked.
- Add progressive delay or CAPTCHA after repeated failures to reduce brute-force risk.
- Verify role-based dashboard redirect behavior for Student, Instructor, and Admin.
- Add tests for session timeout and login audit logging.

---

## Defect report

### BUG-LOGIN-01 · Missing account lockout after repeated failed login attempts

| Field | Details |
| ----- | ------- |
| **ID** | BUG-LOGIN-01 |
| **Title** | Account lockout behavior not implemented after repeated failed login attempts |
| **Type** | Security / Functional |
| **Severity** | High |
| **Use Case Reference** | UC-Login, Alternative Course 2b |
| **Expected** | Lock account after 3 failed attempts and apply progressive delay or block |
| **Observed** | No lockout applied, unlimited login attempts accepted |
| **Impact** | Brute-force attack risk and non-compliance with UC-Login |
| **Evidence** | `screenshots/no_lockout_after_multiple_attempts.png` |

---

## Actions recommended

- [x] Document observations and screenshot evidence.
- [ ] Create an issue for the missing lockout behavior.
- [ ] Confirm role-based dashboard redirect for all user roles.
- [ ] Test the complete password reset link flow.
- [ ] Add tests for session timeout and login audit.

---

## Related documents

- `doc/usecase-diagram/usecases/UC-Login/UC-Login.md`
- `doc/usecase-diagram/usecases/UC-Login/sub_UC-Login/UC-Create_Account.md`
- `doc/usecase-diagram/usecases/UC-Login/sub_UC-Login/UC-Password_Recovery.md`
- `MUGISHO-MERCI-testing-documentation/Use Case Create Account testing create_Account/TEST_REPORT_create_account.md`
- `MUGISHO-MERCI-testing-documentation/test_provide_feedback/TEST_REPORT_student_survey.md`
