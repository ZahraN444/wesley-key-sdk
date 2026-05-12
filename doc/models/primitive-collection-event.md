
# Primitive Collection Event

*This model accepts additional fields of type array.*

## Structure

`PrimitiveCollectionEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventType` | [`?string(EventType2)`](../../doc/models/event-type-2.md) | Optional | - | getEventType(): ?string | setEventType(?string eventType): void |
| `ids` | `int[]` | Required | - | getIds(): array | setIds(array ids): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "eventType": "primitive.variant",
  "ids": [
    77,
    78,
    79
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

