# Employee Documentation

## Create
```json
{
  "employee": {
    "id": 12, // Read only
    "payroll_id":"123", // Optional if skip_for_payroll is true
    "employer_id": 17,
    "created_at": "" // Read only ISO8601 formatted
    "title": "Mr" 
    "forename": "",
    "middle_name": "",
    "surname": "",
    "date_of_birth": "2001-02-01", // YYYY-MM-DD
    "gender": "M", // Either M or F
    "address": {
        
    },
    "personal_email": "",
    "phone_number": "", // Please include country code
    "ni_number": "",
    "is_waiting_for_ni_number": false,
    "national_insurance_category": "A",
    "tax_code": {
    }
    "job_title": "",
    "new_starter": {
    }
    "start_data_submitted": true, // Read only?
    "leaving_date": "2002-03-27",
    "has_left": false // Read only
    "pay_frequency": "", // Either M1 or W1
    "off_payroll_worker": false,
    "hours_worked": null, // Optional used for salaried workers
    "has_student_loan": true,
    "student_loan_type": "" // One of plan_one, plan_two or plan_four
    "has_pension": true,
    "employee_pension_contribution_percentage": 5,
    "employer_pension_contribution_percentage": 3,
    "eligible_for_tax_relief": true, // Read only
    "enrolment_type": "AE" // Read only - todo: check format
    "salary": {} // Deprecated
    "is_director": false,
    "director_config": {}
    "sort_code": "" // 6 digits no dashes
    "account_number": "",
    "is_ready_for_payroll": false // Read only
    "emergency_contact": {}
    "skip_for_payroll": false // Used to signify contractors whose data we store but we do not include in payroll
  }
}
```

- Path: 
`/employee/create`

- HTTP Verb: POST

- Schema: See right hand side

- Response: Complete schema as above

## Update
- Path: `/employee/update`
- HTTP Verb: POST
- Schema: Same as create you just need to provide the employee id