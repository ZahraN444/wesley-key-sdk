## Webhooks Handler

Standard webhook group for order and payment events

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [orderCreated new testing my newy tesingggggg toc hejcjk](../../../doc/events/webhooks/webhooks/order-created-new-testing-my-newy-tesingggggg-toc-hejcjk.md) | Triggered when a new order is created |
| [orderUpdated](../../../doc/events/webhooks/webhooks/order-updated.md) | Triggered when an order is updated |
| [paymentCompleted](../../../doc/events/webhooks/webhooks/payment-completed.md) | Triggered when a payment is successfully processed |
| [primitiveCollectionEvent](../../../doc/events/webhooks/webhooks/primitive-collection-event.md) | Demonstrates oneOf across enum(string), integer, and array types. |

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksHandler;
use WebhooksAndCallbacksAPILib\Models\OrderCreatedEvent;
use WebhooksAndCallbacksAPILib\Models\OrderUpdatedEvent;
use WebhooksAndCallbacksAPILib\Models\PaymentCompletedEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif ($result instanceof OrderCreatedEvent) {
            return response("Received an event of type OrderCreatedEvent: $result");
        } elseif ($result instanceof OrderUpdatedEvent) {
            return response("Received an event of type OrderUpdatedEvent: $result");
        } elseif ($result instanceof PaymentCompletedEvent) {
            return response("Received an event of type PaymentCompletedEvent: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

