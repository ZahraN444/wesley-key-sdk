
# User Action Notification Event

*This model accepts additional fields of type array.*

## Structure

`UserActionNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `userActionNotificationEventType` | `string` | Required, Constant | **Value**: `'user.action'` | getUserActionNotificationEventType(): string | setUserActionNotificationEventType(string userActionNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "userActionNotificationEventType": "user.action",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

