# User Story Template

**Title:**
_As a [user role], I want [feature/goal], so that [reason]._

**Acceptance Criteria:**
1. [Criteria 1]
2. [Criteria 2]
3. [Criteria 3]

**Priority:** [High/Medium/Low]
**Story Points:** [Estimated Effort in Points]
**Notes:**
- [Additional information or edge cases]

## Admin User Stories

### As an admin, I want to log into the portal using my username and password, so that the platform remains secure.

   Acceptance Criteria:

  1. Given the admin has valid credentials (username and password), When the admin click the Login button, Then the admin should be logged into the platform successfully.
  2, Given the admin enters an invalid username or password, When the admin click the Login button, Then the platform should display an error message indicating that the credentials are incorrect.
  3. Given the admin has entered invalid credentials more than 3 times, When the admin attempts to log in again, Then the username should be locked for 1 hour, And the platform should display a message informing the admin that the account has been temporarily blocked.
  
  Priority: High
  
  Story Points: 5
  
  Notes:
  
  - The number of failed login attempts increases if a new failed attempt occurs within 3 hours of the previous failed attempt.
  - When the admin successfully logs into the platform, the number of failed login attempts is reset to zero.

### As an admin, I want to log out of the portal, so that system access is protected.

   Acceptance Criteria:
   
  1. Given the admin is logged into the portal, When the admin presses the Log Out button, Then the platform should terminate the session and display the login screen.
  2. Given the admin has logged out of the platform, When the admin attempts to access a protected page, Then the platform should redirect the admin to the login screen.
  3. Given the admin has logged out, When the admin uses the browser back button, Then the platform should not allow access to authenticated pages.
  
  Priority: High
  
  Story Points: 5
  
  Notes:
  
  - The user session must be fully invalidated after logout.
  - Re-authentication is required to access protected resources after logout.

### As an admin, I want to add doctors to the portal, so that they can provide services to patients through the portal.
Acceptance Criteria:

1. Given the admin is logged into the platform, When the admin enters the required doctor information and presses the Save button, Then the system should create the doctor's profile and store it in the database.
2. Given the admin is creating a doctor profile, When required information is missing, Then the platform should display a validation message and prevent the profile from being created.
3. Given the doctor profile has been successfully created, When the operation is completed, Then the platform should display a confirmation message to the admin.

Priority: High

Story Points: 5

Notes:

- Doctor profiles must include required fields such as name, specialization, and contact information.

- The system should validate the input data before saving it to the database.

### As an admin, I want to delete a doctor's profile from the portal, so that outdated or inactive accounts can be removed from the system. 

Acceptance Criteria:

1. Given the admin is logged into the platform, When the admin selects a doctor profile and presses the Delete button, Then the system should remove the doctor's profile from the platform.
2. Given the admin attempts to delete a doctor profile, When the admin confirms the deletion, Then the system should permanently remove the profile.
3. Given the admin attempts to delete a doctor profile, When the admin cancels the action, Then the doctor profile should remain unchanged.

Priority: Medium

Story Points: 3

Notes:

- A confirmation step should be required before deleting a doctor profile.

- The system should prevent accidental deletions.

### As an admin, I want to run a stored procedure in MySQL to retrieve the number of appointments per month, so that I can track portal usage statistics.

Acceptance Criteria:

1. Given the admin has access to the MySQL CLI, When the admin executes the stored procedure, Then the system should return the number of appointments per month.
2. Given the stored procedure has been executed successfully, When the query results are returned, Then the system should display the number of appointments grouped by month.
3. Given the stored procedure execution fails, When an error occurs, Then the system should display an appropriate error message.

Priority: Medium

Story Points: 3

Notes:

- The stored procedure should retrieve appointment statistics grouped by month.

- The results will be used to monitor platform activity and usage trends.

## Patient User Stories

### As a patient, I want to view a list of doctors without logging in, so that I can explore available options before registering.

Acceptance Criteria:

1. Given the patient is not logged into the portal, When the patient accesses the doctors section, Then the platform should display a list of available doctors.
2. Given the list of doctors is displayed, When the patient views the information, Then basic details such as name and specialization should be visible.

Priority: Medium

Story Points: 3

Notes:

- No authentication is required to view the list of doctors.

- Sensitive information should not be displayed.

### As a patient, I want to sign up using my email and password, so that I can book appointments.

Acceptance Criteria:

1. Given the patient provides valid email and password, When the patient submits the registration form, Then the system should create a new account successfully.
2. Given the patient enters an invalid email format, When the patient submits the form, Then the system should display a validation error message.
3. Given the email is already registered, When the patient attempts to sign up, Then the system should prevent account creation and display an error message.

Priority: High

Story Points: 5

Notes:

- Email must be unique.

- Password should meet minimum security requirements.

### As a patient, I want to log into the portal using my email and password, so that I can manage my appointments.

Acceptance Criteria:

1. Given the patient has valid credentials, When the patient clicks the Login button, Then the patient should be logged into the portal successfully.
2. Given the patient enters invalid credentials, When the patient clicks the Login button, Then the system should display an error message.

Priority: High

Story Points: 5

Notes:

- The same authentication rules defined for admin login apply.

### As a patient, I want to log out of the portal, so that my account remains secure. 

Acceptance Criteria:

1. Given the patient is logged into the portal, When the patient clicks the Log Out button, Then the system should terminate the session and redirect to the login screen.
2. Given the patient has logged out, When the patient attempts to access a protected page, Then the system should redirect the patient to the login screen.

Priority: High

Story Points: 3

Notes:

- Session must be invalidated after logout.

### As a patient, I want to book appointments and view my upcoming appointments, so that I can manage my consultations effectively.

Acceptance Criteria:

1. Given the patient is logged into the portal, When the patient selects a doctor and an available time slot, Then the system should allow the patient to book a one-hour appointment.
2. Given the appointment is successfully booked, When the process is completed, Then the system should display a confirmation message.
3. Given the patient is logged into the portal, When the patient accesses the appointments section, Then the system should display a list of upcoming appointments.
4. Given the appointments are displayed, When the patient views the list, Then each appointment should include date, time, and doctor information.

Priority: High

Story Points: 8

Notes:

- Appointments are fixed to one-hour duration.
- Only available time slots should be selectable.
- Past appointments are not included in the upcoming list.

## Doctor User Stories

### As a doctor, I want to log into the portal, so that I can manage my appointments.

Acceptance Criteria:

1. Given the doctor has valid credentials, When the doctor clicks the Login button, Then the doctor should be logged into the portal successfully.
2. Given the doctor enters invalid credentials, When the doctor clicks the Login button, Then the system should display an error message.

Priority: High

Story Points: 5

Notes:

- The same authentication rules defined for admin login apply.

### As a doctor, I want to log out of the portal, so that my data remains secure. 

Acceptance Criteria:

1. Given the doctor is logged into the portal, When the doctor clicks the Log Out button, Then the system should terminate the session and redirect to the login screen.
2. Given the doctor has logged out, When the doctor attempts to access a protected page, Then the system should redirect the doctor to the login screen.

Priority: High

Story Points: 3

Notes:

- Session must be invalidated after logout.

### As a doctor, I want to view my appointment calendar and mark my unavailability, so that patients can only book available time slots.

Acceptance Criteria:

1. Given the doctor is logged into the portal, When the doctor accesses the calendar section, Then the system should display the doctor's scheduled appointments.
2. Given the doctor is viewing the calendar, When the doctor selects a time slot and marks it as unavailable, Then the system should block that time slot from being booked by patients.
3. Given a time slot is marked as unavailable, When a patient attempts to book that time slot, Then the system should prevent the booking.

Priority: High

Story Points: 8

Notes:

- The calendar should display both booked and unavailable time slots.
- Changes in availability should be reflected immediately in the booking system.

### As a doctor, I want to update my profile information, so that patients have access to accurate and up-to-date details.

Acceptance Criteria:

1. Given the doctor is logged into the portal, When the doctor updates their profile information and submits the changes, Then the system should save the updated information successfully.
2. Given the doctor enters invalid data, When the doctor submits the form, Then the system should display validation errors.

Priority: Medium

Story Points: 3

Notes:

- Profile includes specialization and contact information.
- Data validation must be applied before saving changes.

### As a doctor, I want to view patient details for upcoming appointments, so that I can be prepared for consultations.

Acceptance Criteria:

1. Given the doctor is logged into the portal, When the doctor accesses an upcoming appointment, Then the system should display the patient's relevant details.
2. Given patient details are displayed, When the doctor views the information, Then it should include necessary data such as name and appointment information.

Priority: High

Story Points: 5

Notes:

- Sensitive data must be handled securely.
