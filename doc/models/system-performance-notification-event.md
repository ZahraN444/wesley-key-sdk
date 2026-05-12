
# System Performance Notification Event

*This model accepts additional fields of type array.*

## Structure

`SystemPerformanceNotificationEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `systemPerformanceNotificationEventType` | `string` | Required, Constant | **Value**: `'system.performance'` | getSystemPerformanceNotificationEventType(): string | setSystemPerformanceNotificationEventType(string systemPerformanceNotificationEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "systemPerformanceNotificationEventType": "system.performance",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

