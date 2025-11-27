
# Getting Started with Cypress Test API

## Introduction

This is a sample API to demonstrate an OpenAPI spec with multiple endpoints and a custom model.

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install package-wesley-key@0.1.6
```

For additional package details, see the [Npm page for the package-wesley-key@0.1.6 npm](https://www.npmjs.com/package/package-wesley-key/v/0.1.6).

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

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| defaultHost | `string` | *Default*: `'www.example.com'` |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |

The API client can be initialized as follows:

```ts
import { Client, Environment } from 'package-wesley-key';

const client = new Client({
  timeout: 0,
  environment: Environment.Production,
  defaultHost: 'www.example.com',
});
```

## List of APIs

* [API](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/controllers/api.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/proxy-settings.md)

### HTTP

* [HttpRequest](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/api-response.md)
* [ApiError](https://www.github.com/ZahraN444/wesley-key-sdk/tree/0.1.6/doc/api-error.md)

