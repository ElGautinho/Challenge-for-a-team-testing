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

## 1. What I Was Testing

I was testing the **login (authentication) workflow** for the MKB Survey Application. This covers:

- Accessing the login interface
- Logging in with valid credentials and checking the dashboard redirect
- Handling incorrect credentials (wrong password / user not found)
- Account lockout behavior after multiple failed attempts
- Redirect to role-specific dashboard after successful login
- Forgotten password page accessibility from the login screen

---

## 2. Preconditions (from Use Case)

- The user has access to the login interface.
- The system is connected to the authentication database.
- A test account already exists (created via the Create Account use case).

---

## 3. Test Cases Executed

### TC-01 · Accessing the Login Interface

**Steps:**

1. Opened the MKB Survey Application in the browser.
2. Navigated to the login page.

**Expected result:** A login form is displayed with fields for email and password, a "Forgot password?" link, and a "Create Account" option.

**Observed result:** ✅ The login page loaded correctly with all expected fields and links.

**Screenshot:**

![Login Page](screenshots/login_page.png)

---

### TC-02 · Login with Incorrect Credentials — "User Not Found" Error

**Steps:**

1. On the login page, entered an email address that does not exist in the system.
2. Entered any password.
3. Clicked "Login".

**Expected result (from UC-Login, Alternative Course 2a):** The system displays an error message indicating the credentials are invalid (e.g. _"Incorrect username or password"_ or _"User not found"_).

**Observed result:** ✅ The system displayed a **"user not found"** error message, correctly blocking access for unregistered email addresses.

**Screenshot:**

![User Not Found Error](screenshots/user_not_found_error.png)

---

### TC-03 · No Lockout After Multiple Incorrect Login Attempts

**Steps:**

1. On the login page, entered a valid email but an incorrect password.
2. Repeated the attempt **multiple times** (more than 3 and more than 5 times).
3. Observed the system behavior after each attempt.

**Expected result (from UC-Login, Alternative Course 2b):**

- After **3 failed attempts**: Account is locked for **1 minute**, with message _"Too many failed attempts. Please try again in X minutes."_
- After **5 failed attempts**: Account is locked for **3 minutes**.

**Observed result:** ❌ **The lockout mechanism was NOT triggered.** The system continued accepting login attempts indefinitely without any lockout, warning, or CAPTCHA challenge.

**Type:** Missing Security Feature  
**Severity:** **High** — Without a lockout mechanism, the application is vulnerable to **brute-force attacks**. An attacker could try unlimited password combinations with no consequence.

**Screenshot:**

![No Lockout After Multiple Attempts](screenshots/no_lockout_after_multiple_attempts.png)

---

### TC-04 · Login with Valid Credentials → Dashboard Redirect

**Steps:**

1. On the login page, entered a valid registered email and correct password.
2. Clicked "Login".

**Expected result (from UC-Login, Step 6):** The system verifies the credentials and redirects the user to their **role-specific dashboard** (Student dashboard in this test).

**Observed result:** ✅ The system successfully authenticated the user and redirected to the home / dashboard page after login.

**Screenshot:**

![Dashboard After Login](screenshots/dashboard_after_login.png)

---

### TC-05 · "Forgot Password?" / "Lost Password" Link Accessible 

**Steps:**

1. On the login page, clicked the "Lost your password?" / "Forgot password?" link.

**Expected result (from UC-Login, Section: Forgotten Password Recovery):** The system redirects to the password recovery interface where the user enters their registered email to receive a reset link.

**Observed result:** ✅ The **Lost Password page** loaded correctly and displayed the email input form for password recovery.

**Screenshot:**

![Lost Password Page](screenshots/lost_password_page.png)

---

## 4. Summary Table

| TC ID | Test Case Description                                  | Status  | Severity |
| ----- | ------------------------------------------------------ | ------- | -------- |
| TC-01 | Accessing the login interface                          | ✅ Pass | —        |
| TC-02 | Login with unregistered email — "user not found" error | ✅ Pass | —        |
| TC-03 | **No lockout after multiple failed login attempts**    | ❌ Fail | **High** |
| TC-04 | Login with valid credentials → dashboard redirect      | ✅ Pass | —        |
| TC-05 | "Lost Password" page accessible from login             | ✅ Pass | —        |

## 5. What I Saw

- I verified that the login interface loads correctly and presents the expected fields.
- The application correctly rejects unregistered accounts and successful credentials redirect to the dashboard.
- The password recovery entry point is available and functional.
- The security behavior for multiple failed login attempts is missing, which is a major gap.

## 6. What the UC Says

- UC-Login requires a working authentication flow with valid and invalid credential handling.
- It specifies role-based dashboard redirection and an account lockout policy after repeated failed attempts.
- It also requires the forgotten password recovery path to be accessible.

## 7. What Was Not Respected Compared to the UC

- The lockout policy after repeated failed login attempts was not implemented.
- No CAPTCHA or progressive delay mechanism appeared after multiple failures.
- Role-based dashboard redirect verification was not fully tested in this report and should be confirmed.

## 8. Professional Improvement Proposals

- Implement an account lockout policy after 3–5 failed attempts and show explicit messaging.
- Add a CAPTCHA or progressively increasing wait time on repeated failures to reduce brute-force risk.
- Confirm and document that each role (Student, Instructor, Admin) lands on the correct dashboard.
- Add session timeout and login audit logging for security and traceability.
- Improve the login UI by showing clear validation messages near each form field.

---

## 9. Bug Report

### BUG-01 · No Account Lockout After Multiple Failed Login Attempts

| Field             | Details                                                                 |
| ----------------- | ----------------------------------------------------------------------- |
| **ID**            | BUG-LOGIN-01                                                            |
| **Title**         | Account not locked after multiple failed login attempts                 |
| **Type**          | Missing Security Feature                                                |
| **Severity**      | High                                                                    |
| **Use Case Ref.** | UC-Login — Alternative Course 2b                                        |
| **Expected**      | After 3 failed attempts: 1-min lockout. After 5: 3-min lockout.         |
| **Observed**      | No lockout at all — unlimited attempts accepted without any restriction |
| **Impact**        | The application is vulnerable to brute-force attacks on user accounts   |
| **Screenshot**    | `screenshots/no_lockout_after_multiple_attempts.png`                    |

---

## 6. Special Notes

> ❌ **Critical security gap:** The lockout mechanism (Alternative Course 2b in UC-Login) is a fundamental security requirement, not an optional enhancement. Its absence represents a direct violation of the documented specification and exposes all user accounts to automated password attacks.

> ✅ **Credential validation works correctly:** The system properly identifies unregistered email addresses and blocks login (TC-02).

> ✅ **Successful login flow works end-to-end:** Valid credentials authenticate the user and redirect them to the dashboard (TC-04).

> ✅ **Password recovery entry point works:** The "Lost Password" page is accessible from the login interface (TC-05).

> ⚠️ **Not yet tested in this session:**
>
> - Role-based redirect verification (Student vs. Instructor vs. Admin dashboards)
> - Session timeout enforcement
> - CAPTCHA after repeated failures (supplemental requirement in UC-Login)
> - Clicking the full password reset link from the recovery email

---

## 7. Action Items

- [x] Documented all test observations with screenshots
- [ ] Create a sub-issue for **BUG-LOGIN-01** (missing lockout after failed attempts)
- [ ] Add the **`bug`** label to the sub-issue
- [ ] Test role-based dashboard redirect (Student / Instructor / Admin)
- [ ] Test session timeout enforcement
- [ ] Continue testing the full password recovery flow

---

## 8. Related Documents

- [UC-Login](../../doc/usecase-diagram/usecases/UC-Login/UC-Login.md)
- [UC-Create_Account](../../doc/usecase-diagram/usecases/UC-Login/sub_UC-Login/UC-Create_Account.md)
- [UC-Password_Recovery](../../doc/usecase-diagram/usecases/UC-Login/sub_UC-Login/UC-Password_Recovery.md)
- [Test Report: Create Account](../test_create_account/TEST_REPORT_create_account.md)
- [Test Report: Student Survey](../test_student_survey/TEST_REPORT_student_survey.md)
