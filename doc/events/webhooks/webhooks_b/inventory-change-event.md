
# Inventory Change Event

Triggered when inventory stock levels change

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [InventoryStockIncreaseEvent|InventoryStockDecreaseEvent|InventoryStockDepletedEvent](../../../../doc/models/containers/inventory-change-event-body.md).

## Payload Example

```json
{
  "inventoryStockIncreaseEventType": "stock.increase",
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
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksBHandler;
use WebhooksAndCallbacksAPILib\Models\InventoryStockDecreaseEvent;
use WebhooksAndCallbacksAPILib\Models\InventoryStockDepletedEvent;
use WebhooksAndCallbacksAPILib\Models\InventoryStockIncreaseEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksBHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif (
            $result instanceof InventoryStockIncreaseEvent || $result instanceof InventoryStockDecreaseEvent || $result instanceof InventoryStockDepletedEvent
        ) {
            return response(
                "Received an event of type InventoryStockIncreaseEvent|InventoryStockDecreaseEvent|InventoryStockDepletedEvent: $result"
            );
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
| 200 | Event processed successfully |
| 422 | Event processing failed |

