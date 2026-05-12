
# Order

*This model accepts additional fields of type array.*

## Structure

`Order`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderId` | `?string` | Optional | - | getOrderId(): ?string | setOrderId(?string orderId): void |
| `customerId` | `?string` | Optional | - | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `items` | [`?(OrderItem[])`](../../doc/models/order-item.md) | Optional | - | getItems(): ?array | setItems(?array items): void |
| `totalAmount` | `?float` | Optional | - | getTotalAmount(): ?float | setTotalAmount(?float totalAmount): void |
| `status` | [`?string(Status)`](../../doc/models/status.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `createdAt` | `?DateTime` | Optional | - | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `updatedAt` | `?DateTime` | Optional | - | getUpdatedAt(): ?\DateTime | setUpdatedAt(?\DateTime updatedAt): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "orderId": "order_789",
  "customerId": "cust_12345",
  "totalAmount": 59.98,
  "status": "pending",
  "createdAt": "09/19/2025 10:30:00",
  "updatedAt": "09/19/2025 10:30:00",
  "items": [
    {
      "productId": "productId2",
      "quantity": 22,
      "price": 56.94,
      "description": "description2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

