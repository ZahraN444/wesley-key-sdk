
# Basic Authentication



Documentation for accessing and setting credentials for httpBasic.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| username | `string` | - | `username` |
| passwprd | `string` | - | `passwprd` |



**Note:** Auth credentials can be set using `httpBasicCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'package-wesley-key';

const client = new Client({
  httpBasicCredentials: {
    username: 'username',
    passwprd: 'passwprd'
  },
});
```


