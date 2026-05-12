
# Audit Log Event

Demonstrates an event without signature verification.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [AuditLogEvent](../../../../doc/models/audit-log-event.md).

## Payload Example

```json
{
  "eventType": "audit.log",
  "actor": "actor6",
  "action": "action6",
  "context": {
    "key1": "val1",
    "key2": "val2"
  },
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
use WebhooksAndCallbacksAPILib\Events\UnknownEvent;
use WebhooksAndCallbacksAPILib\Events\Webhooks\WebhooksNoVerificationHandler;
use WebhooksAndCallbacksAPILib\Models\AuditLogEvent;

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $result = WebhooksNoVerificationHandler::parseEvent($request);

        if ($result instanceof AuditLogEvent) {
            return response("Received an event of type AuditLogEvent: $result");
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

