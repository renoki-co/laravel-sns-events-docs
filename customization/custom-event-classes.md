# 🤿 Custom Event Classes

Like the payload, you can also change the event classes to trigger the confirmation or the normal notification.

Simply, replace the following two methods on the extended controller:

```php
/**
 * Get the event class to trigger during subscription confirmation.
 *
 * @return string
 */
protected function getSubscriptionConfirmationEventClass(): string
{
    return CustomSubscriptionConfirmation::class;
}

/**
 * Get the event class to trigger during SNS event.
 *
 * @return string
 */
protected function getNotificationEventClass(): string
{
    return CustomSnsEvent::class;
}
```

&#x20;**Make sure you also use the custom event classes in the `EventServiceProvider` class as described in the **[**Configuring Events**](../getting-started/configuring-events.md)** section.**

To avoid any issues, remember to extend the respective, original event classes before the change. This will save you a lot of time for debugging in case features are added to the original events.

```php
// CustomSnsEvent.php

use Rennokki\LaravelSnsEvents\Events\SnsNotification;

class CustomSnsEvent extends SnsNotification
{
    //
}
```

```php
// CustomSubscriptionConfirmation.php

use Rennokki\LaravelSnsEvents\Events\SnsSubscriptionConfirmation;

class CustomSubscriptionConfirmation extends SnsSubscriptionConfirmation
{
    //
}
```
