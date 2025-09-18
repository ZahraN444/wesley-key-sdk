
# Getting Started with Swagger Petstore

## Introduction

This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.

Find out more about Swagger: [http://swagger.io](http://swagger.io)

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install package-wesley-key@0.1.2
```

For additional package details, see the [Npm page for the package-wesley-key@0.1.2 npm](https://www.npmjs.com/package/package-wesley-key/v/0.1.2).

## Test the SDK

To validate the functionality of this SDK, you can execute all tests located in the `test` directory. This SDK utilizes `Jest` as both the testing framework and test runner.

To run the tests, navigate to the root directory of the SDK and execute the following command:

```bash
npm run test
```

Or you can also run tests with coverage report:

```bash
npm run test:coverage
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| testHeader | `string` | This is a test header<br>*Default*: `'TestHeaderDefaultValue'` |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| apiKeyCredentials | [`ApiKeyCredentials`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/custom-header-signature.md) | The credential object for apiKey |
| httpBasicCredentials | [`HttpBasicCredentials`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/basic-authentication.md) | The credential object for httpBasic |
| petstoreAuthCredentials | [`PetstoreAuthCredentials`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/oauth-2-implicit-grant.md) | The credential object for petstoreAuth |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| production | **Default** |
| environment2 | - |
| environment3 | - |

## Authorization

This API uses the following authentication schemes.

* [`api_key (Custom Header Signature)`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/custom-header-signature.md)
* [`httpBasic (Basic Authentication)`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/basic-authentication.md)
* [`petstore_auth (OAuth 2 Implicit Grant)`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/auth/oauth-2-implicit-grant.md)

## List of APIs

* [Pet](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/controllers/pet.md)
* [Store](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/controllers/store.md)
* [User](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/controllers/user.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/proxy-settings.md)

### HTTP

* [HttpRequest](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/api-response.md)
* [ApiError](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.2/doc/api-error.md)

