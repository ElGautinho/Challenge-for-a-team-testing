# Test Report - Use Case: Instructor Survey Management (UC-Instructor)

| Field | Details |
| --- | --- |
| **Tester** | Mugisho Merci |
| **Application** | MKB Survey Web Application |
| **Use Case** | UC-ManageSurvey / Instructor survey management |
| **Reference** | `doc/usecase-diagram/usecases/UC-ManageSurvey/UC-ManageSurveys.md` |
| **Screenshots Used** | `login instructeur.png`, `Dashborard instructeur.png`, `Screenshot  Add New Survey interface.png`, `Screenshot  all Surveys interface.png`, `Screenshot  all Questions interface .png`, `Screenshot  Survey Responses .png` |

---

## 1. What I tested

- I tested the instructor login screen and confirmed that the instructor access page is visible.
- I tested the instructor dashboard navigation and found the survey management area.
- I checked the survey list view for existing surveys.
- I opened the add survey interface and verified that the survey title, description, and date fields are present.
- I reviewed the question management interface and confirmed that questions are displayed.
- I inspected the survey response view to see how instructor feedback is shown.

## 2. What I observed

- The instructor interface is visible and looks like a typical admin dashboard.
- I can see menu options for Surveys, Questions, and Survey Responses.
- The login and dashboard screens appear functional in the screenshots.
- The survey list shows multiple surveys with a clear option to create a new survey.
- The add new survey screen includes the required fields for title, description, and dates.
- The question list view shows the created questions and question types.
- The survey responses page indicates that instructors can review student answers.

## 3. What the UC says in the document

According to `UC-ManageSurveys.md`, the instructor should be able to:

- Navigate to the survey management section.
- See the list of existing surveys.
- Create a new survey with title, description, opening date, and closing date.
- Add questions and choose question types.
- Edit an existing survey and save changes.
- Delete a survey when needed.
- Preview the survey before finalizing it.
- View survey responses later.

## 4. What is respected compared to the use case

- I found the survey management section and it is accessible from the instructor dashboard.
- I saw a list of surveys, including published surveys.
- I confirmed that the interface allows adding a new survey.
- I verified that question management is available.
- I confirmed the survey response review screen exists.
- The basic workflow of creating surveys and reviewing responses matches the use case.

## 5. What is not fully respected compared to the use case

- I did not see a visible survey preview button in the screenshots.
- I could not confirm the delete survey action from the images.
- The interface looks like a generic admin dashboard, not a custom instructor workflow.
- I did not see clear evidence that opening and closing dates are validated.
- I did not see cohort or instructor-specific management details that are mentioned in some use case texts.

## 6. What I propose as solution

- Add a clear **Preview Survey** button on the survey creation/edit screen.
- Add visible **Delete** and **Save** buttons for survey management.
- Add validation messages for **start date** and **end date** when creating a survey.
- Improve the instructor dashboard labels to show **Instructor Surveys**, **My Questions**, and **Responses**.
- Use the exact terms from the UC document to make the navigation clearer.
- Add a confirmation message that instructors can only view responses for their own surveys.

## 7. Additional improvements for a stronger and more advanced platform

- Add **role-based dashboard personalization** so instructors see only their surveys and responses, while admins see all surveys and management options.
- Implement **real-time validation** on survey fields to prevent invalid input immediately and reduce errors.
- Add **autosave** for survey drafts so instructors do not lose work while creating or editing surveys.
- Add **search and filtering** in survey lists by status, date range, course, or keyword to improve scalability.
- Add **export options** for survey results in CSV or PDF so instructors can share reports with stakeholders.
- Add **activity logs** for survey changes, including who created or edited the survey and when.
- Add **access control checks** on the backend to ensure only the survey owner or authorized roles can edit or delete a survey.
- Add **responsive design improvements** for mobile use, since instructors may access the platform from different devices.
- Add **performance monitoring** for survey loading and response review so the platform remains fast when data grows.
- Add **UI consistency improvements** to avoid confusion between instructor, question, and response screens.
- Consider adding **notifications** for instructors when students complete a survey or when a survey reaches its closing date.
- Add **analytics dashboard elements** for instructors: completion rate, average score, response count, and overdue surveys.

---

## 8. Conclusion

I tested the available instructor screens and found that the main survey creation and review functions are present. The application follows the main UC requirements for survey management, but it needs better evidence of preview, delete, and date validation features to fully meet the documented use case.

**Recommendation**: add the missing buttons and validation fields, then take updated screenshots to confirm the improved workflow. Also add the advanced improvements listed above to make the platform more robust, user-friendly, and future-ready.
