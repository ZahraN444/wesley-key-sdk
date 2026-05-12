
# Package

*This model accepts additional fields of type array.*

## Structure

`Package`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `packageId` | `?string` | Optional | - | getPackageId(): ?string | setPackageId(?string packageId): void |
| `weight` | `?float` | Optional | - | getWeight(): ?float | setWeight(?float weight): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "packageId": "packageId0",
  "weight": 83.8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

