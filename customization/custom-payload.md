# 📦 Custom Payload

Although the event sends an array that contains the message and headers, you may customize the way the final payload (which will be sent to the listeners) will look. This way, you can customize the payloads and send additional data for the listeners.

This is how the payload function looks like by default:

```php
use Illuminate\Http\Request;

/**
 * Get the event payload to stream to the event in case
 * AWS sent a notification payload.
 *
 * @param  array  $snsMessage
 * @param  \Illuminate\Http\Request  $request
 * @return array
 */
protected function getNotificationPayload(array $snsMessage, Request $request): array
{
    // $snsMessage is the SNS message from the request body (as array)
    // You may also access the request.

    return [
        'message' => $snsMessage,
        'headers' => $request->headers->all(),
    ];
}
```

While extending the controller, you can replace the `getNotificationPayload` and `getSubscriptionConfirmationPayload` methods with your own:

```php
use Illuminate\Http\Request;

/**
 * Get the event payload to stream to the event in case
 * AWS sent a notification payload.
 *
 * @param  array  $snsMessage
 * @param  \Illuminate\Http\Request  $request
 * @return array
 */
protected function getNotificationPayload(array $snsMessage, Request $request): array
{
    return [
        'message' => $snsMessage,
        'time_of_request' => now(),
    ];
}

/**
 * Get the event payload to stream to the event in case
 * AWS sent a subscription confirmation payload.
 *
 * @param  array  $snsMessage
 * @param  \Illuminate\Http\Request  $request
 * @return array
 */
protected function getSubscriptionConfirmationPayload(array $snsMessage, Request $request): array
{
    return [
        'message' => $snsMessage,
        'time_of_request' => now(),
    ];
}
```

**Remember that after extending the controller, you have to point the SNS route defined earlier to the new controller.**
