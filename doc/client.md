
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| testHeader | `string` | This is a test header<br>*Default*: `'TestHeaderDefaultValue'` |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](../doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| apiKeyCredentials | [`ApiKeyCredentials`](auth/custom-header-signature.md) | The credential object for apiKey |
| httpBasicCredentials | [`HttpBasicCredentials`](auth/basic-authentication.md) | The credential object for httpBasic |
| petstoreAuthCredentials | [`PetstoreAuthCredentials`](auth/oauth-2-implicit-grant.md) | The credential object for petstoreAuth |

The API client can be initialized as follows:

```ts
import {
  Client,
  Environment,
  OAuthScopePetstoreAuthEnum,
} from 'package-wesley-key';

const client = new Client({
  apiKeyCredentials: {
    'api_key': 'api_key'
  },
  httpBasicCredentials: {
    username: 'username',
    passwprd: 'passwprd'
  },
  petstoreAuthCredentials: {
    oAuthClientId: 'OAuthClientId',
    oAuthRedirectUri: 'OAuthRedirectUri',
    oAuthScopes: [
      OAuthScopePetstoreAuthEnum.Readpets,
      OAuthScopePetstoreAuthEnum.Writepets
    ]
  },
  testHeader: 'TestHeaderDefaultValue',
  timeout: 0,
  environment: Environment.Production,
});
```

