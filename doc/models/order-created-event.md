
# Order Created Event

*This model accepts additional fields of type array.*

## Structure

`OrderCreatedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderId` | `?string` | Required | - | getOrderId(): ?string | setOrderId(?string orderId): void |
| `fulfillmentStatus` | [`string(FulfillmentStatus)`](../../doc/models/fulfillment-status.md) | Required | - | getFulfillmentStatus(): string | setFulfillmentStatus(string fulfillmentStatus): void |
| `trackingNumber` | `?string` | Optional | - | getTrackingNumber(): ?string | setTrackingNumber(?string trackingNumber): void |
| `carrier` | `?string` | Optional | - | getCarrier(): ?string | setCarrier(?string carrier): void |
| `scopes` | [`?(string(OauthScopeOauthACG)[])`](../../doc/models/oauth-scope-oauth-acg.md) | Optional | List of scopes that apply to the OAuth token<br><br>**Constraints**: *Unique Items Required* | getScopes(): ?array | setScopes(?array scopes): void |
| `estimatedDelivery` | `?DateTime` | Optional | - | getEstimatedDelivery(): ?\DateTime | setEstimatedDelivery(?\DateTime estimatedDelivery): void |
| `timestamp` | `?DateTime` | Optional | - | getTimestamp(): ?\DateTime | setTimestamp(?\DateTime timestamp): void |
| `document` | `?string` | Optional | Binary file upload | getDocument(): ?string | setDocument(?string document): void |
| `totalWeight` | `?float` | Optional | - | getTotalWeight(): ?float | setTotalWeight(?float totalWeight): void |
| `price` | `?float` | Optional | - | getPrice(): ?float | setPrice(?float price): void |
| `quantity` | `?int` | Optional | - | getQuantity(): ?int | setQuantity(?int quantity): void |
| `longId` | `?int` | Optional | - | getLongId(): ?int | setLongId(?int longId): void |
| `fragile` | `?bool` | Optional | - | getFragile(): ?bool | setFragile(?bool fragile): void |
| `notes` | `?string` | Optional | Explicitly nullable field | getNotes(): ?string | setNotes(?string notes): void |
| `items` | `?(string[])` | Optional | - | getItems(): ?array | setItems(?array items): void |
| `packages` | [`?(Package[])`](../../doc/models/package.md) | Optional | - | getPackages(): ?array | setPackages(?array packages): void |
| `address` | [`?Address`](../../doc/models/address.md) | Optional | - | getAddress(): ?Address | setAddress(?Address address): void |
| `metadata` | `?array` | Optional | - | getMetadata(): ?array | setMetadata(?array metadata): void |
| `attributes` | `?array<string,string>` | Optional | - | getAttributes(): ?array | setAttributes(?array attributes): void |
| `deliveryDetails` | string\|[DeliveryDetails](../../doc/models/delivery-details.md)\|null | Optional | This is a container for one-of cases. | getDeliveryDetails(): | setDeliveryDetails( deliveryDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "orderId": null,
  "fulfillmentStatus": "fulfilled",
  "carrier": "FedEx",
  "estimatedDelivery": "2025-09-22",
  "timestamp": "09/19/2025 14:00:00",
  "totalWeight": 12.75,
  "price": 199.99,
  "quantity": 5,
  "longId": 9223372036854775807,
  "fragile": true,
  "items": [
    "item1",
    "item2"
  ],
  "packages": [
    {
      "packageId": "PKG123",
      "weight": 2.5
    }
  ],
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "zip": "10001"
  },
  "metadata": {
    "customField1": "value",
    "customField2": 123
  },
  "attributes": {
    "color": "red",
    "size": "XL"
  },
  "deliveryDetails": {
    "method": "express",
    "eta": "2025-09-21T12:00:00Z"
  },
  "trackingNumber": "trackingNumber2",
  "scopes": [
    "file_requests.read"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

