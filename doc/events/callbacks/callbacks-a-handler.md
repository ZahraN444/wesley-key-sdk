## Callbacks A Handler

Payment and fulfillment callback group with custom verification

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [paymentCallback](../../../doc/events/callbacks/callbacks_a/payment-callback.md) | Called when payment processing is complete |
| [fulfillmentCallback](../../../doc/events/callbacks/callbacks_a/fulfillment-callback.md) | Called when order processing is complete |

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
use WebhooksAndCallbacksAPILib\Models\PaymentCallback;

Route::post(
    '/callbacks',
    function (Request $request): Response {
        $handler = CallbacksAHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif ($result instanceof PaymentCallback) {
            return response("Received an event of type PaymentCallback: $result");
        } elseif ($result instanceof FulfillmentCallback) {
            return response("Received an event of type FulfillmentCallback: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

