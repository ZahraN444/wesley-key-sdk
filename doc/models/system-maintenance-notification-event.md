
# System Maintenance Notification Event

*This model accepts additional fields of type array.*

## Structure

`SystemMaintenanceNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `systemMaintenanceNotificationEventType` | `string` | Required, Constant | **Value**: `'system.maintenance'` | getSystemMaintenanceNotificationEventType(): string | setSystemMaintenanceNotificationEventType(string systemMaintenanceNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "systemMaintenanceNotificationEventType": "system.maintenance",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

