
# Root Level Primitive One of Event

Root-level oneOf across primitives and collections of primitives/enums.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [string(RootLevelPrimitiveOneOfEventRequest)|int|string(RootLevelPrimitiveOneOfEventRequest1)[]|int[]](../../../../doc/models/containers/root-level-one-of-primitive-event-root-level-primitive-one-of-body.md).

## Payload Example

```json
"on"
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

Route::post(
    '/webhooks',
    function (Request $request): Response {
        $result = WebhooksNoVerificationHandler::parseEvent($request);

        if (
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

## Accepted Server Responses

The server should responds with one of the following status codes:

| Status Code | Description |
|  --- | --- |
| 200 | Event processed successfully |
| 422 | Event processing failed |

