
# Inventory Stock Increase Event

*This model accepts additional fields of type array.*

## Structure

`InventoryStockIncreaseEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inventoryStockIncreaseEventType` | `string` | Required, Constant | **Value**: `'stock.increase'` | getInventoryStockIncreaseEventType(): string | setInventoryStockIncreaseEventType(string inventoryStockIncreaseEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "inventoryStockIncreaseEventType": "stock.increase",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

