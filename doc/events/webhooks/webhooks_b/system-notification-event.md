
# System Notification Event

Triggered when system-wide notifications occur

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [SystemAlertNotificationEvent|SystemMaintenanceNotificationEvent|SystemPerformanceNotificationEvent](../../../../doc/models/containers/system-notification-event-body.md).

## Payload Example

```json
{
  "systemAlertNotificationEventType": "system.alert",
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
use WebhooksAndCallbacksAPILib\Models\SystemAlertNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\SystemMaintenanceNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\SystemPerformanceNotificationEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksBHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif (
            $result instanceof SystemAlertNotificationEvent || $result instanceof SystemMaintenanceNotificationEvent || $result instanceof SystemPerformanceNotificationEvent
        ) {
            return response(
                "Received an event of type SystemAlertNotificationEvent|SystemMaintenanceNotificationEvent|SystemPerformanceNotificationEvent: $result"
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

