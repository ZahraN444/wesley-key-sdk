
# Webhook Update

*This model accepts additional fields of type array.*

## Structure

`WebhookUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `?string` | Optional | - | getUrl(): ?string | setUrl(?string url): void |
| `events` | `?(string[])` | Optional | - | getEvents(): ?array | setEvents(?array events): void |
| `secret` | `?string` | Optional | - | getSecret(): ?string | setSecret(?string secret): void |
| `active` | `?bool` | Optional | - | getActive(): ?bool | setActive(?bool active): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "url": "url6",
  "events": [
    "events8",
    "events9"
  ],
  "secret": "secret2",
  "active": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

