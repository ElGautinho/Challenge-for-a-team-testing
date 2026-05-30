# Test Report - Use Case: Create Account (UC-Create_Account)

| Field | Details |
| --- | --- |
| **Application** | MKB Survey Web Application |
| **Use Case** | UC-Create_Account |
| **Reference** | `doc/usecase-diagram/usecases/UC-Login/sub_UC-Login/UC-Create_Account.md` |
| **Screenshots Location** | `MUGISHO-MERCI-testing-documentation/Use Case: Create Account testing create_Account/screenshots/` |

---

## 1. What I Tested

- I tested the registration form to see if users can create an account.
- I tested the email validation to check if invalid emails are rejected.
- I tested the role selection (Student or Instructor) to see if the form displays correctly.
- I tested duplicate email handling to confirm that existing emails are blocked.
- I tested the confirmation email flow to verify that users receive an email after registration.
- I tested the password reset feature to ensure users can recover their account.
- I tested the account registration for Students to see if specific fields are collected.
- I tested the registration error messages to verify they guide users correctly.

## 2. What I Observed

- The registration form is accessible and shows basic fields (email, password, name, etc.).
- Invalid email formats are rejected by the system with an error message.
- Duplicate emails are blocked with a message: "An account with this email already exists."
- A confirmation email is sent after successful registration.
- The password reset feature sends a recovery link via email.
- The form shows a success message after email confirmation.
- The Student role is available in the role selection, but specific Student fields (academic level, programming languages) are not shown in the form.
- The home page is visible after registration.
- The system accepts registration and puts accounts in a pending approval state.

## 3. What the UC Says in the Document

According to `UC-Create_Account.md`, the system should:

**For all users:**
- Allow users to access the registration page
- Allow users to select their role (Student or Instructor)
- Validate all required fields and reject invalid input
- Reject duplicate email addresses
- Send a confirmation email after registration
- Put the account in a pending approval state

**For Students specifically:**
- Display a field for academic level
- Display a field for programming languages
- Collect these values during registration

**For Instructors:**
- Proceed without level/language selection
- Await admin assignment to cohorts

**For Administrators:**
- Review registrations
- Approve or reject accounts
- Assign Students to cohorts based on level/language
- Assign Instructors to manage cohorts

## 4. What is Respected Compared to the UC

- The registration form is accessible to users
- Users can select a role (Student or Instructor)
- Email validation works and rejects invalid formats
- Duplicate email detection is working
- Confirmation emails are sent successfully
- The account is set to pending approval after registration
- The home page displays after registration
- The password reset feature works correctly
- The form collects basic user information

## 5. What is NOT Respected Compared to the UC

- **Critical Gap:** The form does not display academic level field for Students
- **Critical Gap:** The form does not display programming languages field for Students
- The form does not show conditional fields based on role selection
- No visible confirmation that Instructors are handled differently from Students
- No visible confirmation that cohort assignment will happen after admin approval
- The registration form appears generic instead of role-specific

## 6. What I Propose as Solutions

### Immediate Solutions (High Priority)

- **Add Student-specific fields:** Implement conditional form fields that appear only when "Student" role is selected:
  - Academic Level dropdown (e.g., Beginner, Intermediate, Advanced)
  - Programming Languages multi-select checkbox (e.g., Python, Java, JavaScript, C++, etc.)

- **Improve form validation:** Add clear error messages for required Student fields before allowing submission

- **Make Student fields required:** Ensure that Students cannot submit the registration form without selecting academic level and programming languages

- **Add role indicator:** Display the selected role prominently in the form to prevent confusion

- **Add preview section:** Show a summary of entered information before final submission

### Medium Priority Solutions

- **Improve email confirmation UX:** Show a countdown timer for email expiration
- **Add role-specific instructions:** Display different instructions for Students vs Instructors
- **Improve error messages:** Make validation messages clearer and more actionable
- **Add field tooltips:** Show helpful information when users hover over fields

### Advanced Solutions

- **Backend validation:** Ensure that all required fields are validated at the database level
- **Email verification redundancy:** Send a verification code via SMS if email delivery fails
- **Cohort pre-assignment:** Show available cohorts based on Student level/languages before approval
- **Account status tracking:** Display the approval status in a dashboard after registration
- **Audit logging:** Log all registration attempts and field submissions for compliance

---

## 7. Summary Table

| Feature | Expected | Observed | Status | Priority |
|---------|----------|----------|--------|----------|
| Registration form access | ✓ | ✓ | PASS | - |
| Role selection | ✓ | ✓ | PASS | - |
| Student academic level field | ✓ | ✗ | FAIL | Critical |
| Student programming languages field | ✓ | ✗ | FAIL | Critical |
| Email validation | ✓ | ✓ | PASS | - |
| Duplicate email rejection | ✓ | ✓ | PASS | - |
| Confirmation email | ✓ | ✓ | PASS | - |
| Pending approval state | ✓ | ✓ | PASS | - |
| Password reset | ✓ | ✓ | PASS | - |

---

## 8. Conclusion

I tested the Create Account use case and found that the basic registration workflow is functional. However, there is a **critical gap:** the form does not collect Student-specific information (academic level and programming languages) as required by the UC document. This missing functionality prevents proper cohort assignment and weakens the Student onboarding experience.

**Overall Status:** PARTIAL PASS with Critical Issues

**Recommendation:** 
1. Implement the Student-specific form fields immediately
2. Add validation for these new required fields
3. Test the complete registration flow again with new screenshots
4. Ensure backend properly stores and uses these values for cohort assignment

### Additional Advanced Solutions for Platform Robustness

#### Security Enhancements
- **Multi-factor authentication (MFA):** Add optional 2FA with email or authenticator app for account security
- **Password strength meter:** Show real-time password strength feedback during registration
- **Prevent common passwords:** Block weak passwords and common dictionary words
- **Rate limiting:** Limit registration attempts per IP address to prevent brute force attacks
- **CAPTCHA integration:** Add reCAPTCHA to prevent bot registrations
- **Account lockout mechanism:** Lock accounts after multiple failed login attempts
- **Session timeout:** Auto-logout after inactivity period to improve security

#### User Experience Improvements
- **Progressive form:** Show form fields progressively instead of all at once
- **Auto-save draft:** Save registration progress locally so users don't lose data
- **Field validation on blur:** Validate email/username availability without submitting form
- **Inline help text:** Show contextual help next to each field
- **Success celebration:** Show a success animation or message after account creation
- **Suggested values:** Auto-suggest academic levels or programming languages based on user profile
- **Mobile-responsive form:** Optimize form for all device sizes with proper touch targets
- **Dark mode support:** Ensure registration form works in dark mode

#### Data Quality & Management
- **Data deduplication:** Detect and merge duplicate accounts if same email with different case
- **Profile completeness indicator:** Show percentage of profile completion
- **Batch import for institutions:** Allow schools/universities to bulk-import student lists
- **Data retention policy:** Automatically delete unconfirmed accounts after 30 days
- **GDPR compliance:** Add consent checkboxes for data processing and privacy policy
- **Export user data:** Allow users to download their registered data in standard formats
- **Anonymization support:** Provide option for anonymous Student registrations if allowed

#### Administrative Features
- **Admin dashboard for registrations:** Show pending, approved, and rejected registrations
- **Bulk approval:** Allow admins to approve multiple registrations at once
- **Rejection reason tracking:** Log why accounts were rejected for future reference
- **Admin notifications:** Notify admins when new registrations arrive
- **Registration analytics:** Show registration trends, sources, completion rates
- **User search:** Allow admins to search registered users by email, name, or cohort
- **Resend confirmation email:** Allow users to request new confirmation email
- **Override pending approval:** Allow admins to manually approve urgent registrations

#### Notifications & Communication
- **Welcome email templates:** Customize welcome emails with institution branding
- **Registration confirmation SMS:** Send confirmation code via SMS as alternative to email
- **Approval notification:** Send email when admin approves registration
- **Rejection notification:** Provide detailed rejection reason when account is denied
- **Email verification reminders:** Send reminders if user hasn't confirmed email after 24 hours
- **Account status change alerts:** Notify user of any status changes to their account

#### Cohort Management Integration
- **Cohort availability display:** Show which cohorts are available during Student registration
- **Prerequisites checking:** Verify Student qualifications match cohort requirements
- **Waiting list functionality:** Auto-add Students to waiting list if cohorts are full
- **Cohort capacity limits:** Prevent over-enrollment in specific cohorts
- **Instructor availability matching:** Show if registered Instructor's schedule matches cohort needs

#### Technical Infrastructure
- **Load testing:** Ensure registration system handles peak traffic (e.g., semester start)
- **Database indexing:** Add indexes on email, username fields for faster lookups
- **Caching layer:** Cache cohort and academic level lists for faster form load
- **API rate limiting:** Protect registration API with per-user rate limits
- **Error recovery:** Implement retry logic for failed email sends
- **Health checks:** Monitor registration service availability and performance
- **Backup validation:** Test that backup registration data can be restored

#### Analytics & Reporting
- **Registration source tracking:** Track where users find the registration page
- **Conversion funnel analysis:** Monitor how many users complete each registration step
- **Time to completion:** Measure average time to complete registration
- **Field abandonment tracking:** Identify which fields cause users to drop out
- **Regional statistics:** Analyze registrations by geographic location
- **Device usage metrics:** Track registration on mobile vs desktop
- **Language preference tracking:** Log preferred language for future localization

#### Integration & API
- **OAuth integration:** Allow registration via Google, GitHub, Microsoft accounts
- **SAML/LDAP support:** Integrate with institutional directory services
- **Webhook notifications:** Send registration events to external systems
- **REST API for registration:** Allow programmatic account creation for partners
- **Webhook security:** Sign webhooks with HMAC for verification
- **Batch API endpoints:** Support bulk registration via API
- **API documentation:** Provide OpenAPI/Swagger documentation for registration API

