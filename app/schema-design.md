## MySQL Database Design
### Table: patients
- id: INT, Primary Key, Auto Increment
- name: VARCHAR, Not Null
- email: VARCHAR, Not Null
- password: VARCHAR, Not Null
- phone: VARCHAR, Not Null
- address: VARCHAR, Not Null

### Table: doctors
- id: INT, Primary Key, Auto Increment
- name: VARCHAR, Not Null
- specialty: VARCHAR, Not Null
- email: VARCHAR, Not Null
- password: VARCHAR, Not Null
- phone: VARCHAR, Not Null
- availableTimes: COLLECTION

### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)

### Table: admin
- id: INT, Primary Key, Auto Increment
- username: VARCHAR, Not Null
- password: VARCHAR, Not Null


## MongoDB Collection Design
### Collection: prescriptions
```json
{
  "_id": "ObjectId('64abc123456')",
  "patientName": "John Smith",
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
```
### Collection: feedback
### Collection: logs
### Collection: messages