
# Order

## Structure

`Order`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `bigint \| undefined` | Optional | - |
| `petId` | `bigint \| undefined` | Optional | - |
| `quantity` | `number \| undefined` | Optional | - |
| `shipDate` | `string \| undefined` | Optional | - |
| `status` | [`Status1Enum \| undefined`](../../doc/models/status-1-enum.md) | Optional | - |
| `complete` | `boolean \| undefined` | Optional | - |

## Example (as JSON)

```json
{
  "id": 180,
  "petId": 220,
  "quantity": 136,
  "shipDate": "2016-03-13T12:52:32.123Z",
  "status": "placed"
}
```

