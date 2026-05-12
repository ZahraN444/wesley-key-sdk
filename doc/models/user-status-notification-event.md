
# User Status Notification Event

*This model accepts additional fields of type array.*

## Structure

`UserStatusNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `userStatusNotificationEventType` | `string` | Required, Constant | **Value**: `'user.status'` | getUserStatusNotificationEventType(): string | setUserStatusNotificationEventType(string userStatusNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "userStatusNotificationEventType": "user.status",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

