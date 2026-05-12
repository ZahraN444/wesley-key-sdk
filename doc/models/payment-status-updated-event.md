
# Payment Status Updated Event

*This model accepts additional fields of type array.*

## Structure

`PaymentStatusUpdatedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentStatusId` | `string` | Required | - | getPaymentStatusId(): string | setPaymentStatusId(string paymentStatusId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "paymentStatusId": "ps_123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

