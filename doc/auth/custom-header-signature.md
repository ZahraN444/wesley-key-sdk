
# Custom Header Signature



Documentation for accessing and setting credentials for ApiKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| X-API-Key | `string` | API key for authentication | `xAPIKey` | `getXAPIKey()` |



**Note:** Auth credentials can be set using `ApiKeyCredentialsBuilder::init()` in `apiKeyCredentials` method in the client builder and accessed through `getApiKeyCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use WebhooksAndCallbacksAPILib\Authentication\ApiKeyCredentialsBuilder;
use WebhooksAndCallbacksAPILib\WebhooksAndCallbacksAPIClientBuilder;

$client = WebhooksAndCallbacksAPIClientBuilder::init()
    ->apiKeyCredentials(
        ApiKeyCredentialsBuilder::init(
            'X-API-Key'
        )
    )
    ->build();
```


