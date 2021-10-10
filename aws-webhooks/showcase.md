# 🙌 Showcase

The package comes with more controllers that will handle each service separately, so you should be implementing different topics for each controller.

You should create a controller that extends one of the package controllers that are displayed below, based on the service you want to get SNS notifications from:

* `\RenokiCo\AwsWebhooks\Http\Controllers\SesWebhook`
* `\RenokiCo\AwsWebhooks\Http\Controllers\CloudwatchWebhook`
* `\RenokiCo\AwsWebhooks\Http\Controllers\EventbridgeWebhook`

A controller that will handle the response for you should be extended & registered in your routes:

```php
use RenokiCo\AwsWebhooks\Http\Controllers\SesWebhook;

class MyAwesomeSesWebhook extends SesWebhook
{
    /**
     * Handle the Bounce event.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onBounce(array $message, array $originalMessage, Request $request)
    {
        // Unsubscribe the user from newsletter in case of bounce.

        foreach ($message['bounce']['bouncedRecipients'] as $recipient) {
            if ($user = User::whereEmail($recipient['emailAddress'])->first()) {
                $user->update([
                    'subscribed' => false,
                ]);
            }
        }
    }
}
```

```php
Route::any('/aws-sns-ses', [MyAwesomeSesWebhook::class, 'handle']);
```

Make sure  to whitelist your route in your `VerifyCsrfToken.php`:

```php
protected $except = [
    // ...
    'aws-sns-ses/',
];
```

If you have registered the route and created an SNS Topic, you should register the URL and click the confirmation button from the AWS Dashboard. In a short while, if you implemented the route well, you'll be seeing that your endpoint is registered.
