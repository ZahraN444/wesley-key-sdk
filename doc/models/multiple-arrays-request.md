
# Multiple Arrays Request

## Structure

`MultipleArraysRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `array1` | `string[]` | Required | An array containing items of type string | getArray1(): array | setArray1(array array1): void |
| `array2` | `?(int[])` | Optional | An array containing items of type integer | getArray2(): ?array | setArray2(?array array2): void |

## Example (as JSON)

```json
{
  "Array1": [
    "Array19",
    "Array10"
  ],
  "Array2": [
    99,
    98,
    97
  ]
}
```

