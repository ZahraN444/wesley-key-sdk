
# Order Item

*This model accepts additional fields of type array.*

## Structure

`OrderItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `productId` | `string` | Required | - | getProductId(): string | setProductId(string productId): void |
| `quantity` | `int` | Required | **Constraints**: `>= 1` | getQuantity(): int | setQuantity(int quantity): void |
| `price` | `float` | Required | **Constraints**: `>= 0` | getPrice(): float | setPrice(float price): void |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "productId": "prod_001",
  "quantity": 2,
  "price": 29.99,
  "description": "Premium Widget",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

