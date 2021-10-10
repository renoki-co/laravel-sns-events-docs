# 📡 Configuring Events

To process the events, you need to register the package events in `EventServiceProvider.php` and declare your listeners that will run the code upon each one:

```php
use Rennokki\LaravelSnsEvents\Events\SnsNotification;
use Rennokki\LaravelSnsEvents\Events\SnsSubscriptionConfirmation;

protected $listen = [
    // ...
    
    SnsNotification::class => [
        SnsNotificationListener::class,
    ],

    SnsSubscriptionConfirmation::class => [
        //
    ],
];
```

```php
class SnsNotificationListener
{
    // ...
    
    public function handle($event)
    {
        // $event->payload is the data passed to the event.

        $content = json_decode($event->payload['message']['Message'], true);
    }
}
```
