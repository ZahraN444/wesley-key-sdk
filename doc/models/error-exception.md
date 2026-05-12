
# Error Exception

*This model accepts additional fields of type array.*

## Structure

`ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `error` | `string` | Required | Error code | getError(): string | setError(string error): void |
| `message` | `string` | Required | Human-readable error message | getMessage(): string | setMessage(string message): void |
| `details` | `?array` | Optional | Additional error details | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "error": "invalid_request",
  "message": "The request body is invalid",
  "details": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

