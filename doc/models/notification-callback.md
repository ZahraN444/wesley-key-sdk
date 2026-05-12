
# Notification Callback

*This model accepts additional fields of type array.*

## Structure

`NotificationCallback`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `notificationType` | `string` | Required | - | getNotificationType(): string | setNotificationType(string notificationType): void |
| `subject` | `string` | Required | - | getSubject(): string | setSubject(string subject): void |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "notificationType": "email",
  "subject": "Order Coonfirmation",
  "message": "msg_email_789",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

