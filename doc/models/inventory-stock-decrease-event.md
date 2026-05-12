
# Inventory Stock Decrease Event

*This model accepts additional fields of type array.*

## Structure

`InventoryStockDecreaseEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `inventoryStockDecreaseEventType` | `string` | Required, Constant | **Value**: `'stock.decrease'` | getInventoryStockDecreaseEventType(): string | setInventoryStockDecreaseEventType(string inventoryStockDecreaseEventType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example (as JSON)

```json
{
  "inventoryStockDecreaseEventType": "stock.decrease",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

