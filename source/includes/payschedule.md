# Payschedule Documentation

## Preview FPS
- Path: `/payschedule/preview-fps`
- HTTP Verb: GET
- Query Params: employer_id
- Response: See sidebar

```json
{
    "fps_xml": "", // XML String in here
    "validation_errors": ["", ""] // Should be empty
}
```

## List Payments
- Path: `/payschedule/list-payments`
- HTTP Verb: GET
- Response: See sidebar

```json
{
    "pay_date": "2021-04-07",
    "payments": [
        {
            "payment": {
                "id": 7,
                "amount_to_be_paid_to_employee": "72.34", // In GBP
            },
        }
    ]
}
```