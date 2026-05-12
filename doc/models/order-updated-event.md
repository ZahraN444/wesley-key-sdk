
# Order Updated Event

*This model accepts additional fields of type array.*

## Structure

`OrderUpdatedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventType` | [`?string(EventType)`](../../doc/models/event-type.md) | Optional | - | getEventType(): ?string | setEventType(?string eventType): void |
| `orderUpdatedId` | `int` | Required | - | getOrderUpdatedId(): int | setOrderUpdatedId(int orderUpdatedId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "orderUpdatedId": 91,
  "eventType": "order.updated",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

