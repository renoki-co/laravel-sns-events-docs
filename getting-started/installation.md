# 🚀 Installation

### Installing the package

Hop into your console and install the package via Composer:

```bash
composer require rennokki/laravel-sns-events
```

### Configure the webhook controller route

A controller that will handle the response for you should be registered in your routes:

```php
use Rennokki\LaravelSnsEvents\Http\Controllers\SnsController;

Route::any('/aws-sns-webhook', [SnsController::class, 'handle']);
```

 Make sure you whitelist your route in `VerifyCsrfToken.php`:

```php
protected $except = [
    // ...
    'aws-sns-webhook/',
];
```

### Create an AWS Account & create an SNS Topic

You will need an AWS account and register an SNS Topic and set up a subscription for HTTP(s) protocol that will point out the route you just registered.

If you have registered the route and created an SNS Topic, you should register the URL and click the confirmation button from the AWS Dashboard. In a short while, if you implemented the route well, you'll be seeing that your endpoint is registered.
