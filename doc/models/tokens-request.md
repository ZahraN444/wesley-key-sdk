
# Tokens Request

## Structure

`TokensRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scopes` | [`string(OAuthScopeOAuthACGEnum)[]`](../../doc/models/o-auth-scope-o-auth-acg-enum.md) | Required | List of scopes that apply to the OAuth token<br><br>**Constraints**: *Unique Items Required* | getScopes(): array | setScopes(array scopes): void |

## Example (as JSON)

```json
{
  "scopes": [
    "file_requests.read",
    "selection",
    "test1"
  ]
}
```

