
# Address

*This model accepts additional fields of type array.*

## Structure

`Address`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `street` | `string` | Required | - | getStreet(): string | setStreet(string street): void |
| `city` | `string` | Required | - | getCity(): string | setCity(string city): void |
| `zip` | `?string` | Optional | - | getZip(): ?string | setZip(?string zip): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "street": "123 Main St",
  "city": "New York",
  "zip": "10001",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

