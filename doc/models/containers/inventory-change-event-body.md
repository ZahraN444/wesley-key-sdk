
# Inventory Change Event Body

## Data Type

`InventoryStockIncreaseEvent|InventoryStockDecreaseEvent|InventoryStockDepletedEvent`

## Cases

| Type |
|  --- |
| [`InventoryStockIncreaseEvent`](../../../doc/models/inventory-stock-increase-event.md) |
| [`InventoryStockDecreaseEvent`](../../../doc/models/inventory-stock-decrease-event.md) |
| [`InventoryStockDepletedEvent`](../../../doc/models/inventory-stock-depleted-event.md) |

## InventoryStockIncreaseEvent

### Initialization Code

#### Example

```php
$value = InventoryStockIncreaseEventBuilder::init()->build();
```

## InventoryStockDecreaseEvent

### Initialization Code

#### Example

```php
$value = InventoryStockDecreaseEventBuilder::init()->build();
```

## InventoryStockDepletedEvent

### Initialization Code

#### Example

```php
$value = InventoryStockDepletedEventBuilder::init()->build();
```

