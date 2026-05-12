## Webhooks C Handler

Primitive and collection variant webhook group.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name |
|  --- |
| [stringEvent](../../../doc/events/webhooks/webhooks_c/string-event.md) |
| [intEvent](../../../doc/events/webhooks/webhooks_c/int-event.md) |
| [numberListEvent](../../../doc/events/webhooks/webhooks_c/number-list-event.md) |
| [stringMapEvent](../../../doc/events/webhooks/webhooks_c/string-map-event.md) |

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksCHandler;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksCHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif (is_string($result)) {
            return response("Received an event of type string: $result");
        } elseif (is_int($result)) {
            return response("Received an event of type int: $result");
        } elseif (is_array($result) && is_float(array_values($result)[0])) {
            return response("Received an event of type float[]: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

