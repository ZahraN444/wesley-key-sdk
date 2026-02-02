
# Item

## Structure

`Item`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | - | getId(): string | setId(string id): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `date` | `DateTime` | Required | - | getDate(): \DateTime | setDate(\DateTime date): void |
| `dateTime` | `DateTime` | Required | - | getDateTime(): \DateTime | setDateTime(\DateTime dateTime): void |
| `decimal` | `float` | Required | - | getDecimal(): float | setDecimal(float decimal): void |
| `long` | `int` | Required | - | getLong(): int | setLong(int long): void |
| `bool` | `bool` | Required | - | getBool(): bool | setBool(bool bool): void |
| `customEnum` | [`string(CustomEnum)`](../../doc/models/custom-enum.md) | Required | - | getCustomEnum(): string | setCustomEnum(string customEnum): void |
| `status` | [`?string(StatusEnum)`](../../doc/models/status-enum.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `jsonObject` | `array` | Required | A generic JSON object | getJsonObject(): array | setJsonObject(array jsonObject): void |
| `animal` | `array` | Required | - | getAnimal(): array | setAnimal(array animal): void |
| `map` | [`array<string,Message>`](../../doc/models/message.md) | Required | - | getMap(): array | setMap(array map): void |

## Example (as JSON)

```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "name": "John Doe",
  "date": "2024-05-24",
  "dateTime": "05/24/2024 12:00:00",
  "decimal": 1234.56,
  "long": 1234567890123,
  "bool": true,
  "CustomEnum": "VALUE3",
  "jsonObject": {
    "key1": "val1",
    "key2": "val2"
  },
  "Animal": {
    "key1": "val1",
    "key2": "val2"
  },
  "Map": {
    "key0": {
      "code": 246,
      "text": "text4"
    },
    "key1": {
      "code": 246,
      "text": "text4"
    },
    "key2": {
      "code": 246,
      "text": "text4"
    }
  },
  "status": "active"
}
```

