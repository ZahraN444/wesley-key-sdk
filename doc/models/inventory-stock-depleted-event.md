
# Inventory Stock Depleted Event

*This model accepts additional fields of type array.*

## Structure

`InventoryStockDepletedEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inventoryStockDepletedEventType` | `string` | Required, Constant | **Value**: `'stock.depleted'` | getInventoryStockDepletedEventType(): string | setInventoryStockDepletedEventType(string inventoryStockDepletedEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "inventoryStockDepletedEventType": "stock.depleted",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

