
# Create Order Request

*This model accepts additional fields of type array.*

## Structure

`CreateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerId` | `string` | Required | Unique identifier for the customer | getCustomerId(): string | setCustomerId(string customerId): void |
| `items` | [`OrderItem[]`](../../doc/models/order-item.md) | Required | **Constraints**: *Minimum Items*: `1` | getItems(): array | setItems(array items): void |
| `callbackUrl` | `string` | Required | URL to receive callback notifications | getCallbackUrl(): string | setCallbackUrl(string callbackUrl): void |
| `document` | `?string` | Optional | Binary file upload | getDocument(): ?string | setDocument(?string document): void |
| `metadata` | `?array` | Optional | Additional order metadata | getMetadata(): ?array | setMetadata(?array metadata): void |
| `attributes` | `?array<string,string>` | Optional | - | getAttributes(): ?array | setAttributes(?array attributes): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "customerId": "cust_12345",
  "items": [
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
  ],
  "callbackUrl": "https://merchant.example.com/callbacks/payment",
  "attributes": {
    "color": "red",
    "size": "XL"
  },
  "document": "data:text/plain;name=dummy_file;base64,",
  "metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

