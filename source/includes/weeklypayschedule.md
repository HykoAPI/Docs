# Payschedule Documentation

## Create
- Path: `/payschedule/weekly/create`
- HTTP Verb: POST
- Schema:
```
{
  "day_of_week": 4 // Sunday is 0, Saturday is 6
}
```
- Response: 
```
{
    "id": 1,
    "day_of_week": 4,
    "current_period_id": 7,
    "employer_id": 4
}
```

## Add Employee to Payschedule
- Path: `/payschedule/weekly/add-employee`
- HTTP Verb: POST
- Schema: See sidebar

```json
{
    "employee_id": 4,
    "pay_schedule_id": 17
}
```