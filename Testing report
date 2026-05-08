# Test Notes – Create Account (Student)

## Purpose of Testing

I tested the Student Account Registration feature based on the use case documentation.

### Scope
- Manual functional testing
- Registration flow for Student users

---

## Preconditions

Before testing, I verified that:

- The application is accessible
- I am not logged in
- The test email is not already registered
- I reviewed the expected behavior from the use case documentation

---

## Test Steps

1. I opened the application homepage

2. I clicked on the "User" button

3. A dropdown menu appeared with:
   - Login
   - Register as a student

4. Since I did not have an account, I clicked on "Register as a student"

---

# Issue 1 – Missing Role Selection

## Expected Behavior

The system should allow the user to choose between:
- Student
- Instructor

## Actual Behavior

Only "Register as a student" is available.

There is no option for Instructor registration.

## Impact

This does not match the use case requirements.

---

## Screenshot

![alt text](<Capture d’écran (152).png>)

---

# Issue 2 – Missing Student Fields

## Expected Behavior

A Student user should select:
- Academic level
- Programming languages

## Actual Behavior

These fields are missing from the registration flow.

The system goes directly to the registration form.

## Impact

Required Student information is skipped.

---

## Continued Steps

After clicking "Register as a student", the application redirected me to a registration form requesting:

- Username
- Email

---

## Screenshot

![alt text](<Capture d’écran (153).png>)

---

## Form Validation

I submitted the form using valid information.

The system displayed the following message:

> "Registration complete. Please check your email, then visit the login page."

This behavior matches the email confirmation step described in the use case.

---

# Issue 3 – Missing Pending Approval Flow

## Expected Behavior

After registration:
- The account should remain in pending status
- Admin approval should be required
- The user should not access the dashboard immediately

## Actual Behavior

The system sends an email allowing the user to:
- Set a password
- Log in immediately
- Access the dashboard directly

## Impact

This bypasses:
- Admin approval
- Pending account state
- Cohort assignment workflow

---

## Screenshot

![alt text](<Capture d’écran (123).png>)
---

# Summary of Issues

| Issue | Type | Severity |
|---|---|---|
| Missing role selection | Functional Gap | High |
| Missing Student fields | Functional Gap | High |
| Missing pending approval flow | Critical Functional Issue | High |

---

# Conclusion

The following areas need improvement:

- Role handling
- Student-specific data collection
- Approval workflow

These issues should be fixed to align the application behavior with the documented use case.