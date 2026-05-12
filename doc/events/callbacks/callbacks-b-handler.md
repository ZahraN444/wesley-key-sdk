## Callbacks B Handler

Notification delivery callback group with discriminator mapping

Events in this group are uniquely identified by the `notificationType` field.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description | Event Identifier |
|  --- | --- | --- |
| [emailNotificationCallback](../../../doc/events/callbacks/callbacks_b/email-notification-callback.md) | Called when email notification delivery is complete | email |
| [smsNotificationCallback](../../../doc/events/callbacks/callbacks_b/sms-notification-callback.md) | Called when SMS notification delivery is complete | sms |

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\Callbacks\CallbacksBHandler;
use WebhooksAndCallbacksAPILib\Events\SignatureVerificationFailure;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Models\NotificationCallback;

Route::post(
    '/callbacks',
    function (Request $request): Response {
        $handler = CallbacksBHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif ($result instanceof NotificationCallback) {
            return response("Received an event of type NotificationCallback: $result");
        } elseif ($result instanceof NotificationCallback) {
            return response("Received an event of type NotificationCallback: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

