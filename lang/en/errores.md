# Errors

### Error structure

Errors will always have the following structure:

```json
{
  "errorMessage": "Error description"
  "path": "/api/v1/som/path",
  "date": 123123123, // UNIX FORMAT
  "errorCode": "undefined.error"
}
```

### Handling HTTP Status Codes

These will be provided by the HTTP status code.

| Http Status Code |                      |
| ---------------- | -------------------- |
| 200              | OK                   |
| 400              | User error           |
| 401              | Authentication error |
| 404              | Resource not found   |
| 500              | Server error         |

### Timeout handling

The maximum defined timeout for a transaction will be 60 seconds.
