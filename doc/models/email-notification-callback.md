
# Email Notification Callback

*This model accepts additional fields of type array.*

## Structure

`EmailNotificationCallback`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageId` | `?string` | Optional | - | getMessageId(): ?string | setMessageId(?string messageId): void |
| `recipientEmail` | `?string` | Optional | - | getRecipientEmail(): ?string | setRecipientEmail(?string recipientEmail): void |
| `status` | [`?string(Status1)`](../../doc/models/status-1.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "messageId": "msg_001",
  "recipientEmail": "user@example.com",
  "status": "sent",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

