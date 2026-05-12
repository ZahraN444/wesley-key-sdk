## Webhooks No Verification Handler

Demo group with no payload verification (unsigned webhooks).

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [auditLogEvent](../../../doc/events/webhooks/webhooks_no_verification/audit-log-event.md) | Demonstrates an event without signature verification. |
| [rootLevelPrimitiveOneOfEvent](../../../doc/events/webhooks/webhooks_no_verification/root-level-primitive-one-of-event.md) | Root-level oneOf across primitives and collections of primitives/enums. |

## SDK Usage Example

```php
<?php

declare(strict_types=1);

use Illuminate\Http\Request;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\Route;
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksNoVerificationHandler;
use WebhooksAndCallbacksAPILib\Models\AuditLogEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $result = WebhooksNoVerificationHandler::parseEvent($request);

        if ($result instanceof AuditLogEvent) {
            return response("Received an event of type AuditLogEvent: $result");
        } elseif (
            is_string($result) || is_int($result) || is_array($result) || is_string(array_values($result)[0]) || is_array($result) || is_int(array_values($result)[0])
        ) {
            return response("Received an event of type string|int|string[]|int[]: $result");
        } elseif ($result instanceof UnknownEvent) {
            return response("Received an unknown event with payload: {$result->getData()}", 400);
        }
        return response("No event processed", 400);
    }
);
```

