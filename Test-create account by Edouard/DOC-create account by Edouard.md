# TEST REPORT — CREATE ACCOUNT (STUDENT)

## 1. Introduction

This document presents the results of the tests performed on the **“Create Account”** use case for the *Student* role, as part of the **Student Survey Application** project.

The objective of these tests is to verify the compliance of the current implementation with the functional and non-functional requirements defined in the Use Case, particularly in terms of:
- data validation  
- collection of role-specific information  
- security  
- consistency of the registration process  

---

## 2. Use Case Reference

### Key Use Case Requirements:

The system must allow:

- role selection (Student / Instructor)  
- for the Student:
  - input of academic level  
  - selection of programming languages  
- validation of entered data  
- verification of email uniqueness  
- secure storage of information  
- sending of a confirmation email  
- setting account status to *pending approval*  
- restricted access before administrator validation  

---

## 3. Test Scope

The tests covered the following elements:

- navigation to the registration interface  
- form behavior  
- field validation  
- password creation process  
- email handling  
- compliance with Student role requirements  

---

## 4. Observed User Experience Summary

The actual observed process is as follows:

1. The user accesses the homepage  
2. Clicks on “Register as a student”  
3. The system only requests:
   - Username  
   - Email  
4. An email is sent to create the password  
5. The user sets their password via a link  
6. The account is created  

---

## 5. Comparative Analysis (Use Case vs Reality)

| Use Case Requirement | Current Implementation | Status |
|---------------------|----------------------|--------|
| Role selection | Present | ✅ Compliant |
| Academic level input | Missing | ❌ Not compliant |
| Programming languages selection | Missing | ❌ Not compliant |
| Valid email verification | Partial (fake emails accepted) | ⚠️ Partial |
| Email uniqueness | Not clearly verified | ⚠️ Uncertain |
| Confirmation email | Present | ✅ Compliant |
| Pending approval status | Not visible | ❌ Not compliant |
| Access restriction before admin approval | Not observed | ❌ Not compliant |

---

## 6. Identified Issues

### 🔴 1. Missing Student Fields

The registration form does not collect essential information defined in the Use Case:

- academic level  
- programming languages  

👉 Impact:
- incomplete data  
- inability to categorize users  
- loss of business value  

---

### 🔴 2. Lack of strict email validation

The system accepts invalid email addresses during registration.

👉 Impact:
- invalid accounts  
- communication issues  
- poor data quality  

---

### 🟡 3. Weak password management

- weak passwords are accepted  
- no confirmation via re-entry  

👉 Impact:
- reduced security  

---

### 🟡 4. Missing visible “Pending Approval” status

The system does not clearly indicate that the account is awaiting validation.

👉 Impact:
- user confusion  
- non-compliance with the Use Case  

---

## 7. Conclusion

The current implementation of the registration process presents several significant gaps compared to the defined Use Case.

The main shortcomings concern:
- collection of Student-specific data  
- data validation  
- certain security aspects  

Improvements are required to ensure:
- functional compliance  
- data quality  
- system security  

---

## 8. Recommendations

- Add required fields (academic level, programming languages)  
- Strengthen email validation  
- Implement a visible “pending approval” status  
- Improve password policy  
- Add password confirmation field  
