
# Sms Notification Callback

*This model accepts additional fields of type array.*

## Structure

`SmsNotificationCallback`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageId` | `?string` | Optional | - | getMessageId(): ?string | setMessageId(?string messageId): void |
| `phoneNumber` | `?string` | Optional | - | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `status` | [`?string(Status2)`](../../doc/models/status-2.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "messageId": "sms_002",
  "phoneNumber": "+15551234567",
  "status": "delivered",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

