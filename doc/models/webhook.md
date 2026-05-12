
# Webhook

*This model accepts additional fields of type array.*

## Structure

`Webhook`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `webhookId` | `?string` | Optional | - | getWebhookId(): ?string | setWebhookId(?string webhookId): void |
| `createdAt` | `?DateTime` | Optional | - | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `updatedAt` | `?DateTime` | Optional | - | getUpdatedAt(): ?\DateTime | setUpdatedAt(?\DateTime updatedAt): void |
| `lastDelivery` | `?DateTime` | Optional | Timestamp of the last successful delivery | getLastDelivery(): ?\DateTime | setLastDelivery(?\DateTime lastDelivery): void |
| `deliveryCount` | `?int` | Optional | Total number of events delivered | getDeliveryCount(): ?int | setDeliveryCount(?int deliveryCount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "webhookId": "webhook_456",
  "createdAt": "09/19/2025 09:00:00",
  "updatedAt": "09/19/2025 09:00:00",
  "deliveryCount": 42,
  "lastDelivery": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

