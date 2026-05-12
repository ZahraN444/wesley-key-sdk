
# Payment Callback

*This model accepts additional fields of type array.*

## Structure

`PaymentCallback`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderId` | `string` | Required | - | getOrderId(): string | setOrderId(string orderId): void |
| `paymentStatus` | [`string(PaymentStatus)`](../../doc/models/payment-status.md) | Required | - | getPaymentStatus(): string | setPaymentStatus(string paymentStatus): void |
| `transactionId` | `string` | Required | - | getTransactionId(): string | setTransactionId(string transactionId): void |
| `amount` | `?float` | Optional | - | getAmount(): ?float | setAmount(?float amount): void |
| `currency` | `?string` | Optional | - | getCurrency(): ?string | setCurrency(?string currency): void |
| `timestamp` | `?DateTime` | Optional | - | getTimestamp(): ?\DateTime | setTimestamp(?\DateTime timestamp): void |
| `failureReason` | `?string` | Optional | Reason for payment failure (if applicable) | getFailureReason(): ?string | setFailureReason(?string failureReason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "orderId": "order_789",
  "paymentStatus": "success",
  "transactionId": "txn_abc123",
  "amount": 59.98,
  "currency": "USD",
  "timestamp": "09/19/2025 10:35:00",
  "failureReason": "failureReason0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

