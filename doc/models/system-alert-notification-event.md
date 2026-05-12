
# System Alert Notification Event

*This model accepts additional fields of type array.*

## Structure

`SystemAlertNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `systemAlertNotificationEventType` | `string` | Required, Constant | **Value**: `'system.alert'` | getSystemAlertNotificationEventType(): string | setSystemAlertNotificationEventType(string systemAlertNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "systemAlertNotificationEventType": "system.alert",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

