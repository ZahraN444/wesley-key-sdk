## Webhooks B Handler

Multi-event webhook group with oneOf payload structures. Uses a message template that also includes a request header pointer.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [userNotificationEvent](../../../doc/events/webhooks/webhooks_b/user-notification-event.md) | Triggered when user-related notifications occur |
| [systemNotificationEvent](../../../doc/events/webhooks/webhooks_b/system-notification-event.md) | Triggered when system-wide notifications occur |
| [inventoryChangeEvent](../../../doc/events/webhooks/webhooks_b/inventory-change-event.md) | Triggered when inventory stock levels change |

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
use WebhooksAndCallbacksAPILib\Models\SystemAlertNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\SystemMaintenanceNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\SystemPerformanceNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\UserActionNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\UserPreferenceNotificationEvent;
use WebhooksAndCallbacksAPILib\Models\UserStatusNotificationEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $handler = WebhooksBHandler::init('hmac-secret-key');
        $result = $handler->verifyAndParseEvent($request);

        if ($result instanceof SignatureVerificationFailure) {
            return response("Received an event with invalid signature: {$result->getErrorMessage()}", 400);
        } elseif (
            $result instanceof UserActionNotificationEvent || $result instanceof UserStatusNotificationEvent || $result instanceof UserPreferenceNotificationEvent
        ) {
            return response(
                "Received an event of type UserActionNotificationEvent|UserStatusNotificationEvent|UserPreferenceNotificationEvent: $result"
            );
        } elseif (
            $result instanceof SystemAlertNotificationEvent || $result instanceof SystemMaintenanceNotificationEvent || $result instanceof SystemPerformanceNotificationEvent
        ) {
            return response(
                "Received an event of type SystemAlertNotificationEvent|SystemMaintenanceNotificationEvent|SystemPerformanceNotificationEvent: $result"
            );
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

