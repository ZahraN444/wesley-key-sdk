# Orders

Order management operations

```php
$ordersApi = $client->getOrdersApi();
```

## Class Name

`OrdersApi`


# Create Order

Creates a new order and triggers callbacks for payment processing

```php
function createOrder(CreateOrderRequest $body): ApiResponse
```

## Authentication

This endpoint requires [ApiKey](../../doc/auth/custom-header-signature.md) **OR** [BearerAuth](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateOrderRequest`](../../doc/models/create-order-request.md) | Body, Required | - |

## Response Type

**201**: Order created successfully

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`Order`](../../doc/models/order.md).

## Related Callbacks

| Name | Description |
|  --- | --- |
| [Payment Callback](../../doc/events/callbacks/callbacks_a/payment-callback.md) | Called when payment processing is complete |
| [Fulfillment Callback](../../doc/events/callbacks/callbacks_a/fulfillment-callback.md) | Called when order processing is complete |
| [Email Notification Callback](../../doc/events/callbacks/callbacks_b/email-notification-callback.md) | Called when email notification delivery is complete |
| [Sms Notification Callback](../../doc/events/callbacks/callbacks_b/sms-notification-callback.md) | Called when SMS notification delivery is complete |

## Example Usage

```php
$body = CreateOrderRequestBuilder::init(
    'cust_12345',
    [
        OrderItemBuilder::init(
            'prod_001',
            2,
            29.99
        )->build()
    ],
    'https://merchant.example.com/callbacks/payment'
)->build();

$ordersApi = $client->getOrdersApi();
$apiResponse = $ordersApi->createOrder($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'Order:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request | [`ErrorException`](../../doc/models/error-exception.md) |

