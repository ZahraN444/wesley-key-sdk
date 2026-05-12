
# Audit Log Event

*This model accepts additional fields of type array.*

## Structure

`AuditLogEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventType` | [`?string(EventType3)`](../../doc/models/event-type-3.md) | Optional | - | getEventType(): ?string | setEventType(?string eventType): void |
| `actor` | `?string` | Optional | - | getActor(): ?string | setActor(?string actor): void |
| `action` | `?string` | Optional | - | getAction(): ?string | setAction(?string action): void |
| `context` | `?array` | Optional | - | getContext(): ?array | setContext(?array context): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "eventType": "audit.log",
  "actor": "actor0",
  "action": "action2",
  "context": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

