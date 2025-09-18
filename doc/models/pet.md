
# Pet

## Structure

`Pet`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `bigint \| undefined` | Optional | - |
| `category` | [`Category2 \| undefined`](../../doc/models/category-2.md) | Optional | - |
| `name` | `string` | Required | - |
| `photoUrls` | `string[]` | Required | - |
| `tags` | [`Tag[] \| undefined`](../../doc/models/tag.md) | Optional | - |
| `status` | [`StatusEnum \| undefined`](../../doc/models/status-enum.md) | Optional | - |

## Example (as JSON)

```json
{
  "id": 120,
  "category": null,
  "name": "name0",
  "photoUrls": [
    "photoUrls5",
    "photoUrls6"
  ],
  "tags": [
    null
  ],
  "status": "available"
}
```

