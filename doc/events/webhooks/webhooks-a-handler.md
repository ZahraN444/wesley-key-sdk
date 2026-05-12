## Webhooks A Handler

Advanced webhook group for payment status events

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [paymentStatusUpdated](../../../doc/events/webhooks/webhooks_a/payment-status-updated.md) | Triggered when a payment status is updated via POST method |
| [paymentStatusCreated](../../../doc/events/webhooks/webhooks_a/payment-status-created.md) | Triggered when a new payment status is created |

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksAHandler;
use WebhooksAndCallbacksAPILib\Models\PaymentStatusCreatedEvent;
use WebhooksAndCallbacksAPILib\Models\PaymentStatusUpdatedEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksAHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif ($result instanceof PaymentStatusUpdatedEvent) {
            return response("Received an event of type PaymentStatusUpdatedEvent: $result");
        } elseif ($result instanceof PaymentStatusCreatedEvent) {
            return response("Received an event of type PaymentStatusCreatedEvent: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

