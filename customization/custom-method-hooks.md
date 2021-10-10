# 🔗 Custom Method Hooks

In case you don't want to handle the SNS events using Laravel Events or simply you can't handle them via Laravel Events, you can handle the methods sent on notification or subscription via controller methods:

```php
use Rennokki\LaravelSnsEvents\Http\Controllers\SnsController;

class CustomSnsController extends SnsController
{
    /**
     * Handle logic at the controller level on notification.
     *
     * @param  array  $snsMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onNotification(array $snsMessage, Request $request): void
    {
        //
    }

    /**
     * Handle logic at the controller level on subscription.
     *
     * @param  array  $snsMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onSubscriptionConfirmation(array $snsMessage, Request $request): void
    {
        //
    }
}
```
