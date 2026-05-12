
# Webhook Registration

*This model accepts additional fields of type array.*

## Structure

`WebhookRegistration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `string` | Required | The endpoint URL that will receive webhook events | getUrl(): string | setUrl(string url): void |
| `events` | [`string(Event)[]`](../../doc/models/event.md) | Required | List of events to subscribe to | getEvents(): array | setEvents(array events): void |
| `secret` | `?string` | Optional | Secret key for webhook signature verification | getSecret(): ?string | setSecret(?string secret): void |
| `active` | `?bool` | Optional | Whether the webhook is active<br><br>**Default**: `true` | getActive(): ?bool | setActive(?bool active): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "url": "https://merchant.example.com/webhooks/events",
  "events": [
    "order.created",
    "payment.completed"
  ],
  "secret": "webhook_secret_key_123",
  "active": true,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

