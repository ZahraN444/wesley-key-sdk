
# Payment Completed Event

*This model accepts additional fields of type array.*

## Structure

`PaymentCompletedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eventType` | [`?string(EventType1)`](../../doc/models/event-type-1.md) | Optional | - | getEventType(): ?string | setEventType(?string eventType): void |
| `paymentId` | `int` | Required | - | getPaymentId(): int | setPaymentId(int paymentId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "paymentId": 91,
  "eventType": "payment.completed",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

