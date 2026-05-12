
# Getting Started with Webhooks and Callbacks API

## Introduction

A comprehensive API demonstrating webhooks and callbacks patterns.

### Webhooks

Webhooks allow your application to receive real-time notifications when certain events occur.

### Callbacks

Callbacks are used for asynchronous operations where the API will call back to your provided URL when the operation completes.

## Install the Package

Run the following command to install the package and automatically add the dependency to your composer.json file:

```bash
composer require "gallagher-suarez-traders/wesley-key-sdkabc:4.0.0"
```

Or add it to the composer.json file manually as given below:

```json
"require": {
    "gallagher-suarez-traders/wesley-key-sdkabc": "4.0.0"
}
```

You can also view the package at:
https://packagist.org/packages/gallagher-suarez-traders/wesley-key-sdkabc#4.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `50` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524, 408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT', 'GET', 'PUT'` |
| loggingConfiguration | [`LoggingConfigurationBuilder`](doc/logging-configuration-builder.md) | Represents the logging configurations for API calls |
| proxyConfiguration | [`ProxyConfigurationBuilder`](doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| apiKeyCredentials | [`ApiKeyCredentials`](doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |
| bearerAuthCredentials | [`BearerAuthCredentials`](doc/auth/oauth-2-bearer-token.md) | The Credentials Setter for OAuth 2 Bearer token |

The API client can be initialized as follows:

```php
use WebhooksAndCallbacksAPILib\Logging\LoggingConfigurationBuilder;
use WebhooksAndCallbacksAPILib\Logging\RequestLoggingConfigurationBuilder;
use WebhooksAndCallbacksAPILib\Logging\ResponseLoggingConfigurationBuilder;
use Psr\Log\LogLevel;
use WebhooksAndCallbacksAPILib\Authentication\ApiKeyCredentialsBuilder;
use WebhooksAndCallbacksAPILib\Authentication\BearerAuthCredentialsBuilder;
use WebhooksAndCallbacksAPILib\WebhooksAndCallbacksAPIClientBuilder;

$client = WebhooksAndCallbacksAPIClientBuilder::init()
    ->apiKeyCredentials(
        ApiKeyCredentialsBuilder::init(
            'X-API-Key'
        )
    )
    ->bearerAuthCredentials(
        BearerAuthCredentialsBuilder::init(
            'AccessToken'
        )
    )
    ->loggingConfiguration(
        LoggingConfigurationBuilder::init()
            ->level(LogLevel::INFO)
            ->requestConfiguration(RequestLoggingConfigurationBuilder::init()->body(true))
            ->responseConfiguration(ResponseLoggingConfigurationBuilder::init()->headers(true))
    )
    ->build();
```

## Authorization

This API uses the following authentication schemes.

* [`ApiKey (Custom Header Signature)`](doc/auth/custom-header-signature.md)
* [`BearerAuth (OAuth 2 Bearer token)`](doc/auth/oauth-2-bearer-token.md)

## List of APIs

* [Orders](doc/controllers/orders.md)

## Webhooks

* [Webhooks](doc/events/webhooks/webhooks-handler.md)
* [Webhooks A](doc/events/webhooks/webhooks-a-handler.md)
* [Webhooks B](doc/events/webhooks/webhooks-b-handler.md)
* [Webhooks C](doc/events/webhooks/webhooks-c-handler.md)
* [Webhooks No Verification](doc/events/webhooks/webhooks-no-verification-handler.md)

## SDK Infrastructure

### Configuration

* [ProxyConfigurationBuilder](doc/proxy-configuration-builder.md)
* [LoggingConfigurationBuilder](doc/logging-configuration-builder.md)
* [RequestLoggingConfigurationBuilder](doc/request-logging-configuration-builder.md)
* [ResponseLoggingConfigurationBuilder](doc/response-logging-configuration-builder.md)

### HTTP

* [HttpRequest](doc/http-request.md)

### Utilities

* [ApiResponse](doc/api-response.md)

