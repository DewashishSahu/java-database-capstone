# User Stories

## Admin User Stories

---

**Title:**  
_As an admin, I want to log into the portal with my username and password, so that I can manage the platform securely._

**Acceptance Criteria:**  
1. Admin can access login page  
2. Login requires valid credentials  
3. Successful login redirects to admin dashboard  

**Priority:** High  
**Story Points:** 3  
**Notes:** Standard authentication flow

---

**Title:**  
_As an admin, I want to log out of the portal, so that system access is protected._

**Acceptance Criteria:**  
1. Logout option is visible on dashboard  
2. Clicking logout ends the session  
3. Redirects to login page  

**Priority:** High  
**Story Points:** 2  
**Notes:** Include session timeout handling

---

**Title:**  
_As an admin, I want to add doctors to the portal, so that they can start managing appointments._

**Acceptance Criteria:**  
1. Admin can view an 'Add Doctor' form  
2. Form includes fields for name, email, and specialization  
3. Submitting form saves doctor in the system  

**Priority:** High  
**Story Points:** 3  
**Notes:** Include form validation

---

**Title:**  
_As an admin, I want to delete a doctor's profile, so that I can remove inactive users._

**Acceptance Criteria:**  
1. Admin can view doctor list  
2. Each doctor entry has a delete button  
3. System confirms deletion before proceeding  

**Priority:** Medium  
**Story Points:** 2  
**Notes:** Add safety confirmation modal

---

**Title:**  
_As an admin, I want to run a stored procedure to get the number of appointments per month, so that I can track platform usage._

**Acceptance Criteria:**  
1. Stored procedure exists in MySQL  
2. Admin can trigger it from CLI  
3. Result displays appointment count by month  

**Priority:** Low  
**Story Points:** 3  
**Notes:** Output can be logged or displayed in CLI

---

## Patient User Stories

---

**Title:**  
_As a patient, I want to view a list of doctors without logging in, so that I can explore options before registering._

**Acceptance Criteria:**  
1. Public page displays doctors list  
2. Info includes name, specialization, and availability  
3. No login required  

**Priority:** High  
**Story Points:** 2  
**Notes:** Cache doctor data for faster load

---

**Title:**  
_As a patient, I want to sign up with email and password, so that I can book appointments._

**Acceptance Criteria:**  
1. Signup page available  
2. Fields include email, password, name  
3. Successful signup stores patient info  

**Priority:** High  
**Story Points:** 3  
**Notes:** Use hashed passwords

---

**Title:**  
_As a patient, I want to log into the portal, so that I can manage my bookings._

**Acceptance Criteria:**  
1. Login page is accessible  
2. Email/password validated  
3. Redirect to patient dashboard  

**Priority:** High  
**Story Points:** 2  
**Notes:** Basic authentication with token support

---

**Title:**  
_As a patient, I want to log out of the portal, so that my account is secure._

**Acceptance Criteria:**  
1. Logout button is visible  
2. Clears session or JWT  
3. Redirects to homepage  

**Priority:** High  
**Story Points:** 1  
**Notes:** Handle auto logout on inactivity

---

**Title:**  
_As a patient, I want to book an hour-long appointment, so that I can consult with a doctor._

**Acceptance Criteria:**  
1. Patient selects doctor and time  
2. Booking duration is 1 hour  
3. Confirmation shown on success  

**Priority:** High  
**Story Points:** 3  
**Notes:** Prevent double-booking

---

**Title:**  
_As a patient, I want to view my upcoming appointments, so that I can prepare accordingly._

**Acceptance Criteria:**  
1. Dashboard shows upcoming appointments  
2. Each entry includes date, time, and doctor  
3. Sort by date  

**Priority:** Medium  
**Story Points:** 2  
**Notes:** Use calendar UI component

---

## Doctor User Stories

---

**Title:**  
_As a doctor, I want to log into the portal, so that I can manage my appointments._

**Acceptance Criteria:**  
1. Login form accepts doctor credentials  
2. Successful login shows doctor dashboard  
3. Invalid credentials show error  

**Priority:** High  
**Story Points:** 2  
**Notes:** Use role-based redirection

---

**Title:**  
_As a doctor, I want to log out of the portal, so that my data is protected._

**Acceptance Criteria:**  
1. Logout button ends session  
2. Redirects to login  
3. Secure session clearing  

**Priority:** High  
**Story Points:** 1  
**Notes:** Include inactivity timeout

---

**Title:**  
_As a doctor, I want to view my appointment calendar, so that I stay organized._

**Acceptance Criteria:**  
1. Calendar UI available  
2. Appointments shown by date/time  
3. Filters available  

**Priority:** High  
**Story Points:** 4  
**Notes:** Use third-party calendar library

---

**Title:**  
_As a doctor, I want to mark my unavailability, so that patients see only available slots._

**Acceptance Criteria:**  
1. Form to block time slots  
2. Unavailable slots hidden from patient view  
3. Success message shown  

**Priority:** Medium  
**Story Points:** 3  
**Notes:** Check for overlapping appointments

---

**Title:**  
_As a doctor, I want to update my profile with specialization and contact info, so that patients have up-to-date details._

**Acceptance Criteria:**  
1. Profile page with editable fields  
2. Save changes button  
3. Data updated in backend  

**Priority:** Medium  
**Story Points:** 2  
**Notes:** Validate email/phone format

---

**Title:**  
_As a doctor, I want to view patient details for upcoming appointments, so that I can be prepared._

**Acceptance Criteria:**  
1. Appointment list includes patient info  
2. Click on appointment shows details  
3. Include reason for visit  

**Priority:** Medium  
**Story Points:** 3  
**Notes:** Respect patient privacy

---
