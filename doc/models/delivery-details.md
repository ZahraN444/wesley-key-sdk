
# Delivery Details

*This model accepts additional fields of type array.*

## Structure

`DeliveryDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | `?string` | Optional | - | getMethod(): ?string | setMethod(?string method): void |
| `eta` | `?DateTime` | Optional | - | getEta(): ?\DateTime | setEta(?\DateTime eta): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "method": "method6",
  "eta": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

