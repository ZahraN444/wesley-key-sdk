
# User Preference Notification Event

*This model accepts additional fields of type array.*

## Structure

`UserPreferenceNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `userPreferenceNotificationEventType` | `string` | Required, Constant | **Value**: `'user.preference'` | getUserPreferenceNotificationEventType(): string | setUserPreferenceNotificationEventType(string userPreferenceNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "userPreferenceNotificationEventType": "user.preference",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

