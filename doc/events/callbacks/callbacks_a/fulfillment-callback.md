
# Fulfillment Callback

Called when order processing is complete

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [FulfillmentCallback](../../../../doc/models/fulfillment-callback.md).

## Payload Example

```json
{
  "orderId": null,
  "fulfillmentStatus": "fulfilled",
  "carrier": "FedEx",
  "estimatedDelivery": "2025-09-22",
  "timestamp": "2025-09-19T14:00:00Z",
  "totalWeight": 12.75,
  "price": 199.99,
  "quantity": 5,
  "longId": 9223372036854775807,
  "fragile": true,
  "items": [
    "item1",
    "item2"
  ],
  "packages": [
    {
      "packageId": "PKG123",
      "weight": 2.5
    }
  ],
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "zip": "10001"
  },
  "metadata": {
    "customField1": "value",
    "customField2": 123
  },
  "attributes": {
    "color": "red",
    "size": "XL"
  },
  "deliveryDetails": {
    "method": "express",
    "eta": "2025-09-21T12:00:00Z"
  },
  "fulfillmentStatuss": "fulfilled",
  "carrierr": "FedEx",
  "estimatedDeliveryy": "2025-09-22",
  "timestampp": "2025-09-19T14:00:00Z",
  "trackingNumber": "trackingNumber4",
  "scopes": [
    "test1",
    "selection",
    "file_requests.read"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\Callbacks\CallbacksAHandler;
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Models\FulfillmentCallback;

Route::post(
    '/callbacks',
    function (Request $request): Response {
        $handler = CallbacksAHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif ($result instanceof FulfillmentCallback) {
            return response("Received an event of type FulfillmentCallback: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

## Accepted Server Responses

The server should responds with one of the following status codes:

| Status Code | Description |
|  --- | --- |
| 200 | Callback acknowledged |
| 422 | Callback processing failed |

