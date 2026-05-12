
# Payment Status Created Event

*This model accepts additional fields of type array.*

## Structure

`PaymentStatusCreatedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentStatusCreatedId` | `string` | Required | - | getPaymentStatusCreatedId(): string | setPaymentStatusCreatedId(string paymentStatusCreatedId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "paymentStatusCreatedId": "ps_123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

