# Smart Clinic Management System – Schema Design

This document describes the database design for the Smart Clinic Management System.
The system uses:
- **MySQL** for structured, relational data
- **MongoDB** for flexible, document-based data

---

## MySQL Database Design

MySQL is used for core operational data that is structured, validated, and highly relational.

### Table: admin
- id: BIGINT, Primary Key, Auto Increment
- username: VARCHAR(50), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL

Purpose:
Stores administrator credentials for managing the clinic platform.

---

### Table: doctor
- id: BIGINT, Primary Key, Auto Increment
- name: VARCHAR(100), NOT NULL
- specialty: VARCHAR(50), NOT NULL
- email: VARCHAR(100), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL
- phone: VARCHAR(10), NOT NULL

Purpose:
Stores doctor information and credentials.

---

### Table: doctor_available_times
- id: BIGINT, Primary Key, Auto Increment
- doctor_id: BIGINT, Foreign Key → doctor(id)
- available_time: VARCHAR(30), NOT NULL

Purpose:
Tracks individual availability slots for each doctor.
Each doctor can have multiple available time slots.

---

### Table: patient
- id: BIGINT, Primary Key, Auto Increment
- name: VARCHAR(100), NOT NULL
- email: VARCHAR(100), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL
- phone: VARCHAR(10), NOT NULL
- address: VARCHAR(255), NOT NULL

Purpose:
Stores patient personal and contact details.

---

### Table: appointment
- id: BIGINT, Primary Key, Auto Increment
- doctor_id: BIGINT, Foreign Key → doctor(id)
- patient_id: BIGINT, Foreign Key → patient(id)
- appointment_time: DATETIME, NOT NULL
- status: INT, NOT NULL  
  (0 = Scheduled, 1 = Completed, 2 = Cancelled)

Purpose:
Represents a scheduled meeting between a patient and a doctor.

Design considerations:
- Appointments depend on both doctor and patient.
- Past appointments should be retained for reporting and history.
- Overlapping appointments should be prevented at the application level.

---

## MongoDB Collection Design

MongoDB is used for flexible and semi-structured data that may evolve over time.

### Collection: prescriptions

Prescriptions are stored in MongoDB because medication details, doctor notes, and metadata
can vary greatly between appointments.

```json
{
  "_id": "ObjectId('64abc123456')",
  "patientName": "Rahul Verma",
  "appointmentId": 1,
  "medications": [
    {
      "name": "Paracetamol",
      "dosage": "500mg",
      "frequency": "Every 6 hours",
      "durationDays": 5
    }
  ],
  "doctorNotes": "Take medicine after meals and drink plenty of fluids.",
  "tags": ["fever", "pain"],
  "metadata": {
    "issuedBy": "Dr. Amit Sharma",
    "refillAllowed": true,
    "createdAt": "2026-02-09T10:30:00Z"
  }
}
